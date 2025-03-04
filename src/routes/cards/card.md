---
layout: cardLayout
---

<script>
  import Htwo from '../utils/Htwo.svelte'
  import ExampleDiv from '../utils/ExampleDiv.svelte'
  import TableProp from '../utils/TableProp.svelte'
  import TableDefaultRow from '../utils/TableDefaultRow.svelte'
  import { Card, Button, Breadcrumb } from '$lib/index';
  import componentProps from '../props/Card.json'
  // Props table
  let items = componentProps.props
	let propHeader = ['Name', 'Type', 'Default']
	
	let divClass='w-full relative overflow-x-auto shadow-md sm:rounded-lg py-4'
let theadClass ='text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-white'

  const btn1 = ()　=>　{
    alert('You clicked.')
  }

  let crumbs = [
    {
      label:'Home',
      href:'/'
    },
    {
      label:'Cards',
      href:'/cards/'
    },
    {
      label:'Card default',
      href:'/cards/card'
    },
  ]
</script>

<Breadcrumb {crumbs}/>

<h1 class="text-3xl w-full dark:text-white py-8">Card</h1>

<Htwo label="Set up" />

<p>Import Card in the script tag.</p>

```html
<script>
  import { Card } from "flowbite-svelte";
</script>
```

<Htwo label="Examples" />

<ExampleDiv class="flex justify-center">
  <Card header="Simple card with header and content">
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio
    consequatur modi ab nisi perferendis placeat natus repellendus officiis
    ipsa.
    </p>
  </Card>
</ExampleDiv>

```html
<Card header="Simple card with header and content">
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio.
  </p>
</Card>
```

<Htwo label="Card with a link" />

<ExampleDiv class="flex justify-center">
  <Card header="Card with link" link="/" btnLabel="Read more">
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio
    consequatur modi ab nisi perferendis placeat natus repellendus officiis
    ipsa.
    </p>
  </Card>
</ExampleDiv>

```html
<Card header="Card with link" link="/" btnLabel="Read more">
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio.
  </p>
</Card>
```

<Htwo label="Card with a link and image" />

<ExampleDiv class="flex justify-center">
  <Card img="/images/image-1.jpeg" header="Card with link and image" link="/" btnLabel="Read more">
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio
    consequatur modi ab nisi perferendis placeat natus repellendus officiis
    ipsa.
    </p>
  </Card>
</ExampleDiv>

```html
<Card img="/images/image-1.jpeg" header="Card with link and image" link="/" btnLabel="Read more">
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio.
  </p>
</Card>
```

<Htwo label="Card with an image" />

<ExampleDiv class="flex justify-center">
  <Card img="/images/image-2.jpeg" header="Card with image" btnLabel="Read more">
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio
    consequatur modi ab nisi perferendis placeat natus repellendus officiis
    ipsa.
    </p>
  </Card>
</ExampleDiv>

```html
<Card img="/images/image-2.jpeg" header="Card with image">
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio.
  </p>
</Card>
```

<Htwo label="Card with a Button component" />

<p>If you need a click handler rather than a link, use a Button component.</p>

<ExampleDiv class="flex justify-center">
  <Card
    img="/images/image-1.jpeg"
    header="Button component"
    btnLabel="Read more"
  ><span slot="paragraph">
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" >
    Lorem ipsum dolor sit amet consectetur adipisicing elit.
    </p>
    <div class="w-full pt-4">
      <Button name="Click me" on:click={btn1} />
    </div>
    </span>
  </Card>
</ExampleDiv>

```html
<script>
  const btn1 = ()　=>　{
    alert('You clicked.')
  }
</scipt>
<Card
  img="/images/image-1.jpeg"
  header="Button component"
  btnLabel="Read more"
><span slot="paragraph">
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" >
  Lorem ipsum dolor sit amet consectetur adipisicing elit.
  </p>
  <div class="w-full pt-4">
    <Button name="Click me" on:click={btn1} />
  </div>
  </span>
</Card>
```

<Htwo label="Card with yellow button" />

<ExampleDiv class="flex justify-center">
  <Card
    img="/images/image-1.jpeg"
    header="Yellow button"
    link="/"
    btnColor="yellow"
    btnLabel="Read more"
  >
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio.
    </p>
  </Card>
</ExampleDiv>

```html
<Card
  img="/images/image-1.jpeg"
  header="Yellow button"
  link="/"
  btnColor="yellow"
  btnLabel="Read more"
>
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio.
  </p>
</Card>
```

<Htwo label="Card with purple button" />

<ExampleDiv class="flex justify-center">
  <Card
    img="/images/image-1.jpeg"
    header="Purple button"
    link="/"
    btnColor="purple"
    btnLabel="Read more"
  >
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio
    consequatur modi ab nisi perferendis placeat natus repellendus officiis
    ipsa.
  </p>
  </Card>
</ExampleDiv>

```html
<Card
  img="/images/image-1.jpeg"
  header="Purple button"
  link="/"
  btnColor="purple"
  btnLabel="Read more"
>
  <p class="mb-3 font-normal text-gray-700 dark:text-gray-400" slot="paragraph">
  Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla distinctio
  consequatur modi ab nisi perferendis placeat natus repellendus officiis
  ipsa.
  </p>
</Card>
```

<Htwo label="Props" />

<p>The component has the following props, type, and default values. See <a href="/pages/types">types 
 page</a> for type information.</p>

<TableProp header={propHeader} {divClass} {theadClass}>
  <TableDefaultRow {items} rowState='hover' />
</TableProp>