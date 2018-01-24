# vue-simple-switch

## Install:
``` bash
npm i -S vue-simple-switch
```

## Component Example:
``` vue
<template>
<div id="app">
    <vue-simple-switch v-model="isSwitchedOn" />
</div>
</template>

<script>
import VueSimpleSwitch from 'vue-simple-switch'

export default {
  name: 'app',
  components: {
    VueSimpleSwitch
  },
  data () {
    return {
      isSwitchedOn: true
    }
  }
}
</script>
```

## Available props:
Prop Name | Type | Default Value | Prop Description
-- | -- | -- | --
value | Boolean | false | 1-way databinding
color | String | #5d9cec | Set switch color
disabled | Boolean | false | Set disabled
readonly | Boolean | false | Set readonly. Use in combination with :value prop, not v-model
required | Boolean | false | Set required

## More examples:
``` vue
<vue-simple-switch v-model="isSwitchedOn1" />
<vue-simple-switch :value="isSwitchedOn2" />
<vue-simple-switch :value="isSwitchedOn3" readonly />
<vue-simple-switch v-model="isSwitchedOn4" disabled />
<vue-simple-switch v-model="isSwitchedOn5" color="#ff902b" required />
```
**[Live Demo](https://operkh.github.io/vue-simple-switch/)**
