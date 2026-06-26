# uni-select-field

[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/uni-select-field) [![DeepScan grade](https://deepscan.io/api/teams/16372/projects/31958/branches/1037935/badge/grade.svg)](https://deepscan.io/dashboard#view=project&tid=16372&pid=31958&bid=1037935)

&lt;uni-select-field /> is an encapsulated Web Component built upon the foundation of the uniopen design language.

Implementation is straightforward: simply slot a standard `select` element inside &lt;uni-select-field />. The component instantly applies a user interface that aligns seamlessly with the uniopen design language guidelines. Furthermore, its visual styles can be dynamically adapted via native HTML attributes or JavaScript properties.

![<uni-select-field />](https://blog.lalacube.com/mei/img/preview/uni-select-field.png)

## Basic Usage

&lt;uni-select-field /> is a web component. All we need to do is put the required script into your HTML document. Then follow &lt;uni-select-field />'s html structure and everything will be all set.


- Required Script

  ```html
  <script
    type="module"
    src="https://unpkg.com/uni-select-field/mjs/wc-uni-select-field.js">        
  </script>
  ```

- Structure

  Put &lt;uni-select-field /> into HTML document. It will have different functions and looks with attribute mutation.

  ```html
  <uni-select-field subject="Subject" message="Supporting text">
    <select
      slot="select"
      name="my-select"
      required
    >
      <option value="" disabled selected>Please select</option>
      <hr />
      <option value="first">First Value</option>
      <option value="second">Second Value</option>
      <option value="third">Third Value</option>
      <option value="third">Fourth Value (make it longer)</option>
    </select>
  </uni-select-field>
  ```

&lt;uni-select-field /> dynamically adjusts its user interface and core functionality by strictly adhering to the attributes of the encapsulated `select` element. Developers can leverage these capabilities and observe the corresponding behavioral shifts by modifying standard attributes—such as `disabled`, and `required`—directly on the select element.

```html
<uni-select-field>
  <select
    slot="select"
    name="my-select"
    required
  >
    <option value="" disabled selected>Please select</option>
    <hr />
    <option value="first">First Value</option>
    <option value="second">Second Value</option>
    <option value="third">Third Value</option>
    <option value="third">Fourth Value (make it longer)</option>
  </select>
</uni-select-field>
```

## JavaScript Instantiation

&lt;uni-select-field /> could also use JavaScript to create DOM element. Here comes some examples.

```html
<script type="module">
import { UniSelectField } from 'https://unpkg.com/uni-select-field/mjs/wc-uni-select-field.js';

const selectTemplate = document.querySelector('.my-select-template');

// use DOM api
const nodeA = document.createElement('uni-select-field');
document.body.appendChild(nodeA);
nodeA.appendChild(selectTemplate.content.cloneNode(true));

// new instance with Class
const nodeB = new UniSelectField();
document.body.appendChild(nodeB);
nodeB.appendChild(selectTemplate.content.cloneNode(true));
</script>
```

## Style Customization

Developers could apply styles to decorate &lt;uni-select-field />'s looking.

```html
<style>
uni-select-field {
  --uni-select-field-border-color-normal: transparent;
  --uni-select-field-border-color-disabled: var(--ct_input-general_dim_container_default);
  --uni-select-field-border-color-valid: var(--ct_text_success_general);
  --uni-select-field-border-color-invalid: var(--ct_text_danger_general);
  --uni-select-field-border-color-outline: var(--ct_input-general_main_stroke_default);

  --uni-select-field-background-color-normal: var(--ct_input-general_dim_container_default);
  --uni-select-field-background-color-readonly: var(--ct_input-general_dim_container_default);
  --uni-select-field-background-color-disabled: var(--ct_input-general_dim_container_default);

  --uni-select-field-text-color-normal: var(--ct_text_main_general);
  --uni-select-field-text-color-readonly: var(--ct_text_main_general);
  --uni-select-field-text-color-disabled: var(--ct_text_main_pale);
  --uni-select-field-text-color-invalid: var(--ct_text_danger_general);

  --uni-select-field-message-color-normal: var(--ct_text_main_subtle);
  --uni-select-field-message-color-valid: var(--ct_text_success_general);
  --uni-select-field-message-color-invalid: var(--ct_text_danger_general);

  --uni-select-field-caret-color-normal: var(--ct_icon_main_subtle); 
  --uni-select-field-caret-color-disabled: var(--ct_icon_main_pale);

  --uni-select-field-subject-color: var(--ct_text_main_subtle);
}
</style>
```

&lt;uni-select-field /> also leverages the CSS ::part() selector, enabling developers to directly customize and style the icon.

```html
<style>
uni-select-field {
  &::part(icon-subject) {
    ...
  }
}
</style>
```

## Attributes

&lt;uni-select-field /> component exposes a curated set of attributes, enabling developers to dynamically adjust the user interface. This provides the flexibility to tailor the component’s appearance to seamlessly adapt to any given context.

- **size**

  The  `size` attribute configures the overall dimensions of &lt;uni-select-field />. The component currently supports three standard options: `large`, `medium`, and `small`, defaulting to `medium`.

  ```html
  <uni-select-field
    size="large"
  >
    <select
      slot="select"
      name="my-select"
      required
    >
      <option value="" disabled selected>Please select</option>
      <hr />
      <option value="first">First Value</option>
      <option value="second">Second Value</option>
      <option value="third">Third Value</option>
      <option value="third">Fourth Value (make it longer)</option>
    </select>
  </uni-select-field>
  ```

- **subject**

  The `subject` attribute controls the dynamic rendering of the subject content on &lt;uni-select-field />. By default, it is set to an empty string, meaning no content will be displayed.

  ```html
  <uni-select-field
    subject="Your subject"
  >
    <select
      slot="select"
      name="my-select"
      required
    >
      <option value="" disabled selected>Please select</option>
      <hr />
      <option value="first">First Value</option>
      <option value="second">Second Value</option>
      <option value="third">Third Value</option>
      <option value="third">Fourth Value (make it longer)</option>
    </select>
  </uni-select-field>
  ```

  - **message**

  The `message` attribute controls the dynamic rendering of the message content on &lt;uni-select-field />. By default, it is set to an empty string, meaning no content will be displayed.

  ```html
  <uni-select-field
    message="Your message content"
  >
    <select
      slot="select"
      name="my-select"
      required
    >
      <option value="" disabled selected>Please select</option>
      <hr />
      <option value="first">First Value</option>
      <option value="second">Second Value</option>
      <option value="third">Third Value</option>
      <option value="third">Fourth Value (make it longer)</option>
    </select>
  </uni-select-field>
  ```

- **stat**

  Through variations in the `stat` attribute, &lt;uni-select-field /> can dynamically transition between `valid` and `invalid` visual states, providing users with clear feedback on input correctness. By default, it is set to an empty string, which represents the standard, neutral state.

  ```html
  <uni-select-field
    stat="invalid"
  >
    <select
      slot="select"
      name="my-select"
      required
    >
      <option value="" disabled selected>Please select</option>
      <hr />
      <option value="first">First Value</option>
      <option value="second">Second Value</option>
      <option value="third">Third Value</option>
      <option value="third">Fourth Value (make it longer)</option>
    </select>
  </uni-select-field>
  ```

- **appearance**

  Currently, &lt;uni-select-field /> supports two distinct visual variants: `filled` and `outlined`. Developers can utilize the appearance attribute to configure the desired layout, which defaults to `filled`.

  ```html
  <uni-select-field
    appearance="outlined"
  >
    <select
      slot="select"
      name="my-select"
      required
    >
      <option value="" disabled selected>Please select</option>
      <hr />
      <option value="first">First Value</option>
      <option value="second">Second Value</option>
      <option value="third">Third Value</option>
      <option value="third">Fourth Value (make it longer)</option>
    </select>
  </uni-select-field>
  ```

## Properties

| Property Name | Type | Description |
| ----------- | ----------- | ----------- |
| size | String | Getter / Setter size. `size` configures the overall dimensions of &lt;uni-select-field />. The component currently supports three standard options: `large`, `medium`, and `small`, defaulting to `medium`. |
| subject| String | Getter / Setter subject. `subject` controls the dynamic rendering of the subject content on &lt;uni-select-field />. By default, it is set to an empty string, meaning no content will be displayed. |
| message| String | Getter / Setter message. `message` controls the dynamic rendering of the message content on &lt;uni-select-field />. By default, it is set to an empty string, meaning no content will be displayed. |
| stat| String | Getter / Setter stat. `stat` can dynamically transition between `valid` and `invalid` visual states, providing users with clear feedback on input correctness. By default, it is set to an empty string, which represents the standard, neutral state. |
| appearance| String | Getter / Setter appearance. `appearance` supports two distinct visual variants: `filled` and `outlined`. Developers can utilize the appearance attribute to configure the desired layout, which defaults to `filled`. |

## Method
| Mathod Signature | Description |
| ----------- | ----------- |
| refresh() | Force a UI refresh on &lt;uni-select-field />. |

## Reference
- [&lt;uni-select-field /> demo](https://blog.lalacube.com/mei/webComponent_uni-select-field.html)
