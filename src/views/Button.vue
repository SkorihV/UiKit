<script setup>
import Button from "@/components/Button.vue";

function eventClick(e) {
  console.log(e)
}

</script>

<template>
  <h1 class="heading-1">Button</h1>
    <h2 class="header-2">Colors</h2>
    <div class="line">
        <Button label="Primary" color="primary"/>
        <Button label="Secondary" color="second"/>
        <Button label="success" color="success"/>
        <Button label="Info" color="info"/>
        <Button label="Warning" color="warning"/>
        <Button label="Danger" color="danger"/>
    </div>

    <h2 class="header-2">Rounded</h2>
    <div class="line">
        <Button label="Primary" color="primary" rounded/>
        <Button label="Secondary" color="second" rounded/>
        <Button label="success" color="success" rounded/>
        <Button label="Info" color="info" rounded/>
        <Button label="Warning" color="warning" rounded/>
        <Button label="Danger" color="danger" rounded/>
    </div>

    <h2 class="header-2">disabled</h2>
    <div class="line">
        <Button label="Primary" color="primary" disabled/>
        <Button label="Secondary" color="second" disabled/>
        <Button label="success" color="success" disabled/>
        <Button label="Info" color="info" disabled/>
        <Button label="Warning" color="warning" disabled/>
        <Button label="Danger" color="danger" disabled/>
    </div>

    <h2 class="header-2">outlined</h2>
    <div class="line">
        <Button label="Primary" color="primary" outlined/>
        <Button label="Secondary" color="second" outlined/>
        <Button label="success" color="success" outlined/>
        <Button label="Info" color="info" outlined/>
        <Button label="Warning" color="warning" outlined/>
        <Button label="Danger" color="danger" outlined/>
    </div>

    <h2 class="header-2">Icon</h2>
    <div class="line">
        <Button color="primary" icon="fa-heart"/>
        <Button color="second" icon="fa-hand"/>
        <Button color="success" icon="fa-address-book"/>
        <Button color="info" icon="fa-credit-card"/>
        <Button color="warning" icon="fa-lemon"/>
        <Button color="danger" icon="fa-hourglass"/>
    </div>
    <h2 class="header-2">size</h2>
    <div class="line">
        <Button color="primary" icon="fa-heart" size="large"/>
        <Button color="second" icon="fa-hand"/>
        <Button label="success" size="large"/>
        <Button color="info" icon="fa-credit-card"/>
        <Button color="warning" icon="fa-lemon" size="large"/>
        <Button label="Danger" color="danger" @click="eventClick"/>
    </div>
</template>
