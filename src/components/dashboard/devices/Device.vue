<template>
  <div id="device" class="d-inline-block float-left">
    <Thermostat101 v-if="device.type === 'esp8266_thermostat'" :device="device"/>
    <Thermostat101 v-if="device.type === 'esp8266_thermostat_plus'" :device="device"/>

    <Thermostat102 v-if="device.type === 'esp8266_air'" :device="device"/>
    <Thermostat102 v-if="device.type === 'airconditioner'" :device="device"/>

    <Thermostat103 v-if="device.type === 'esp32_panel_4inch'" :device="device"/>
  </div>
</template>

<script>
  import Thermostat101 from "./Thermostat101";
  import Thermostat102 from "./Thermostat102";
  import Thermostat103 from "./Thermostat103";

  export default {
    name: "Device",
    components: {
      Thermostat101,
      Thermostat102,
      Thermostat103,
    },
    props: ['device'],
  }
</script>

<style lang="scss">
  #device {
    background: #2c3041;
    border: 0;

    @media (min-width: 1265px) {
      & {
        margin: var(--percent-width);
        border-radius: var(--percent-width);
      }
    }
    @media (max-width: 1264px) {
      & {
        margin: calc(var(--percent-width) * 1);
        border-radius: calc(var(--percent-width) * 1.25);
      }
    }
    @media (max-width: 960px) {
      & {
        margin: calc(var(--percent-width) * 1.6);
        border-radius: calc(var(--percent-width) * 1.5);
      }
    }
    @media (max-width: 600px) {
      & {
        margin: calc(var(--percent-width) * 2);
        border-radius: calc(var(--percent-width) * 2);
      }
    }
  }
</style>