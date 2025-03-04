---
layout: formLayout
---

<script>
import Htwo from '../utils/Htwo.svelte'
import ExampleDiv from '../utils/ExampleDiv.svelte'
import TableProp from '../utils/TableProp.svelte'
import TableDefaultRow from '../utils/TableDefaultRow.svelte'
import { onMount } from 'svelte';
import { Input, Iconinput, Breadcrumb } from "$lib/index"
import { AtSymbol , Mail } from 'svelte-heros'
import componentProps1 from '../props/Input.json'
let items1 = componentProps1.props
import componentProps2 from '../props/Iconinput.json'
let items2 = componentProps2.props
let propHeader = ['Name', 'Type', 'Default']
let divClass='w-full relative overflow-x-auto shadow-md sm:rounded-lg py-4'
let theadClass ='text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-white'
let ref

onMount(() => {
  ref.focus();
});

  let crumbs = [
    {
      label:'Home',
      href:'/'
    },
    {
      label:'Forms',
      href:'/forms/'
    },
    {
      label:'Input',
      href:'/forms/input'
    }
  ]
</script>

<Breadcrumb {crumbs}/>

<h1 class="text-3xl w-full dark:text-white py-8">Input Components</h1>

<p>The Input component allows you to change the input size, add disabled, helper text, and floating label.</p>

<Htwo label="Sizes" />

<p>User the size prop to change the input size. Choose one from 'sm:text-md' | 'text-sm' | 'sm:text-xs'. The default size is text-sm.</p>

<Htwo label="Examples" />

<ExampleDiv>
<Input class="mb-6"
  id="large-input"
  name="size"
  type="text"
  size="sm:text-md"
  value="large"
  placeholder="Write your text here."
  label="Large input"
  required
  />
<Input class="mb-6" placeholder="Base input" label="Base input"/>
<Input class="mb-6" size="sm:text-xs" placeholder="Small input" label="Small input"/>
</ExampleDiv>

```html
<script>
import { Input } from 'flowbite-svelte'
</script>
<Input
  class="mb-6"
  id="large-input"
  name="size"
  type="text"
  size="sm:text-md"
  value="large"
  placeholder="Write your text here."
  label="Large input"
  required
  />
<Input class="mb-6" placeholder="Base input" label="Base input"/>
<Input class="mb-6" size="sm:text-xs" placeholder="Small input" label="Small input"/>
```

<Htwo label="Focus on load" />

<p>To focus on an input field and a textarea field on load create a `ref` variable and bind it in an Input component. Add a `onMount` function as followings.</p>

<p>In the next example, when you reload/refresh the page, the First name field is focused on load.</p>

<p>If you want to use this on your website, your link to the page must have `rel="external"`.</p>

<ExampleDiv>
<Input class="mb-6" placeholder="First name" label="First name" bind:ref />
<Input class="mb-6" placeholder="Last name" label="Last name" />
</ExampleDiv>

```html
<script>
import { onMount } from 'svelte';
let ref

onMount(() => {
  ref.focus();
});
</script>

<Input class="mb-6" placeholder="First name" label="First name" bind:ref/>
<Input class="mb-6" placeholder="Last name" label="Last name"/>
```

<Htwo label="Disabled" />

<p>Add the disabled prop to change the input to disabled.</p>

<ExampleDiv>
<Input class="mb-6" disabled placeholder="disabled input" label="Disabled input"/>
<Input class="mb-6" disabled readonly placeholder="disabled readonly" label="Disabled readonly input"/>
</ExampleDiv>

```html
<Input class="mb-6" disabled placeholder="disabled input" label="Disabled input"/>
<Input class="mb-6" disabled readonly placeholder="disabled readonly" label="Disabled readonly input"/>
```

<Htwo label="Helper text" />

<p>Use the helper prop to add your helper text. You can use HTML in the helper text.</p>

<ExampleDiv>
<Input label="Email" id="email" name="email" required placeholder="Your email" helper="You can add helper text in <b>HTML</b>."/>
</ExampleDiv>

```html
<Input label="Email" id="email" name="email" required placeholder="Your email" helper="You can add helper text in <b>HTML</b>."/>
```

<Htwo label="Icon input" />

<p>With the Iconinput component, you can add <a href="https://flowbite-svelte.vercel.app/icons/heroicons">Heroicons</a> or <a href="https://flowbite-svelte.vercel.app/icons/simple-icons">Simple-icons</a>. Use iconClass to modify the icon color.</p>

<ExampleDiv>
<Iconinput id="email" type="email" name="email" placeholder="Your email" label="Border" icon={AtSymbol} iconClass="h-4 w-4 mr-2 text-blue-500 dark:text-red-500"/>
<div class="py-4">
<Iconinput noBorder id="email" type="email" name="email" label="No border" icon={Mail} iconClass="h-4 w-4 mr-2 text-blue-500 dark:text-green-500"/>
</div>
</ExampleDiv>

```html
<script>
  import { Iconinput } from 'flowbite-svelte'
</script>
<Iconinput id="email" type="email" name="email" placeholder="Your email" label="Border" icon={AtSymbol} iconClass="h-4 w-4 mr-2 text-blue-500 dark:text-red-500"/>
<div class="py-4">
<Iconinput noBorder id="email" type="email" name="email" label="No border" icon={Mail} iconClass="h-4 w-4 mr-2 text-blue-500 dark:text-green-500"/>
```

<Htwo label="Props" />

<p>The component has the following props, type, and default values. See <a href="/pages/types">types 
 page</a> for type information.</p>

<h3>Input</h3>

<TableProp header={propHeader} {divClass} {theadClass}>
  <TableDefaultRow items={items1} rowState='hover' />
</TableProp>

<h3>Iconinput</h3>

<TableProp header={propHeader} {divClass} {theadClass}>
  <TableDefaultRow items={items2} rowState='hover' />
</TableProp>

