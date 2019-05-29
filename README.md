# Better Laravel Vue form

## Installation

-   npm
    `npm install better-laravel-vue-form --save`

-   yarn
    `yarn add better-laravel-vue-form`

## Usage

```vue
<template>
    <div>
        <input v-model="form.test" type="text" />

        <button @click="submit">send</button>
    </div>
</template>

<script>
import Form from 'better-laravel-vue-form'

export default {
    data: () => ({
        form: new Form({})
    }),

    methods: {
        submit() {
            this.form.post('/test').then(({ data }) => console.log(data))
        }
    }
}
</script>
```

## Validation

To verify if exists any error for a specific field and then, get the error value

```vue
<template>
    <div>
        <input v-model="form.test" type="text" :class="{ 'is-invalid': form.errors.has('test') }" />
        <small v-if="form.errors.has('test')">{{ form.errors.get('test') }}</small>

        <button @click="submit">send</button>
    </div>
</template>

<script>
import Form from 'better-laravel-vue-form'

export default {
    data: () => ({
        form: new Form({})
    }),

    methods: {
        submit() {
            this.form.post('/test').then(({ data }) => console.log(data))
        }
    }
}
</script>
```

## Credits

Developed by DevSquad Team
