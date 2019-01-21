# @evatechsoft/vue-awesome-form

> a vue form component just like json-editor

## Install

``` bash
# npm/yarn
npm install @evatechsoft/vue-awesome-form 
yarn add @evatechsoft/vue-awesome-form
```

## Use

register the component
``` js
import Vue from 'vue'
import SchemaForm from '@evatechsoft/vue-awesome-form'
import '@evatechsoft/vue-awesome-form/dist/main.css'

Vue.component('schema-form', SchemaForm)
```

use in component
```html
<schema-form
  ref="schemaForm"
  :schema="formData.schema"
  :value="formData.value"
></schema-form>
```

CDN
```html
<script src="https://unpkg.com/@evatechsoft/vue-awesome-form@latest/dist/main.js"></script>
<script src="https://unpkg.com/@evatechsoft/vue-awesome-form@latest/dist/main.css"></script>
```

Props:

schema:an object like this

```json
    "register": {
        "type": "TheTree",
        "title": "register",
        "properties": {
            "name": {
                "type": "TheInput",
                "title": "name",
                "rules": {
                    "required": true,
                    "message": "The name cannot be empty"
                }
            },
            "location": {
                "type": "TheTree",
                "title": "address",
                "propertyOrder": 3,
                "properties": {
                    "province": {
                        "type": "TheInput",
                        "title": "province",
                        "rules": {
                            "required": true,
                            "message": "The province cannot be empty"
                        }
                    },
                    "city": {
                        "type": "TheInput",
                        "title": "city",
                        "rules": {
                            "required": true,
                            "message": "The city cannot be empty"
                        }
                    }
                }
            }
        }
    }
```

value: the initValue of the form

```json
"register": {
    "name": "wqe",
    "location": {
      "province": "beijing",
      "city": "beijing"
    }
}
```

methods:

validate: validate the form and return the result and the value of the form

resetFields: reset the form to init value

```js
handleSubmit() {
  this.$refs.schemaForm.validate((err, values) => {
    if(err) {
      console.log('fail');
    } else {
      console.log('succ', values);
    }
  })
},
handleReset() {
  this.$refs.schemaForm.resetFields();
}
```

## Contributors

fightingm <https://github.com/fightingm>
Karan More <https://github.com/karan3112>
Chandan Pasunoori <https://github.com/etsrepo>

## Demo

the following demo contains all the functions of the component and the supported form items.

demo： <https://jsrun.net/bKgKp/embedded/all/light/>

This [article](https://juejin.im/post/5b1cdd29e51d4506bb3a771d) introduces the detailed implementation of this component. 
