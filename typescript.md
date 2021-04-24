# TypeScript snippets

## `ei` - export a interface

generates `export interface ... {...}`.

```typescript typescriptreact
/**
 * ${2:document}
 */
export interface ${1:name} {
  ${3:fields}
}

```

## `eie` - export a interface that extends a type

generates `export interface ... extends ... {...}`.

```typescript typescriptreact
/**
 * ${3:document}
 */
export interface ${1:name} extends ${2:base} {
  ${4:fields}
}

```

## `ec` - export a class

generates `export class ... {...}`.

```typescript typescriptreact
/**
 * ${2:document}
 */
export class ${1:name} {
  ${3:fields}
}

```

## `eec` - export a class that extends a class

generates `export class ... implements ... {...}`

```typescript typescriptreact
/**
 * ${3:document}
 */
export class ${1:name} extends ${2:base} {
  ${4:fields}
}

```

## `eci` - export a class that implemented a interface

generates `export class ... implements ... {...}`

```typescript typescriptreact
/**
 * ${3:document}
 */
export class ${1:name} implements ${2:interface} {
  ${4:implements}
}

```

## `ecei` - export a class that extends a class and implemented a interface

generates `export class ... extends ... implements ... {...}`

```typescript typescriptreact
/**
 * ${4:document}
 */
export class ${1:name} extends ${2:base} implements ${3:interface} {
  ${5:implements}
}

```

## `eac` - export a abstract class

generates `export abstract class ... {...}`

```typescript typescriptreact
/**
 * ${2:document}
 */
export abstract class ${1:name} {
  ${3:fields}
}

```

## `eace` - export a abstract class that extends a class

generates `export abstract class ... extends ... {...}`

```typescript typescriptreact
/**
 * ${3:document}
 */
export abstract class ${1:name} extends ${2:baes} {
  ${4:fields}
}

```

## `eaci` - export a abstract class that implemented a interface

generates `export abstract class ... implements ... {...}`

```typescript typescriptreact
/**
 * ${3:document}
 */
export abstract class ${1:name} implements ${2:interface} {
  ${4:fields}
}

```

## `eacei` - export a abstract class that extends a class and implemented a interface

generates `export abstract class ... extends ... implements ... {...}`

```typescript typescriptreact
/**
 * ${4:document}
 */
export abstract class ${1:name} extends ${2:base} implements ${3:interface} {
  ${5:fields}
}

```

## `et` - export a type

generates `export type ... = ...`

```typescript typescriptreact
/**
 * ${2:document}
 */
export type ${1:name} = ${3:type}

```

## `eot` - export a object type

generates `export type ... = {...}`

```typescript typescriptreact
/**
 * ${2:document}
 */
export type ${1:name} = {
  ${3:fields}
}

```

## `eft` - export a function type

generates `export type ... = (...) => {...}`

```typescript typescriptreact
/**
 * ${2:document}
 */
export type ${1:name} = (${3:arguments}) => ${4:return_type}

```

## `eaf` - export a arrow function

```typescript typescriptreact
${3:document}
export const ${1:name} = (${2:arguments}): ${4:return_type} => {
  ${5:body}
}

```

## `eaaf` - export a async arrow function

```typescript typescriptreact
${3:document}
export const ${1:name} = async (${2:arguments}): ${4:return_type} => {
  ${5:body}
}

```

## `etaf` - export a typed arrow function

```typescript typescriptreact
${4:document}
export const ${1:name}: ${2:type} = (${3:arguments}) => {
  ${5:body}
}

```

## `etaaf` - export a typed async arrow function

```typescript typescriptreact
${4:document}
export const ${1:name}: ${2:type} = async (${3:arguments}) => {
  ${5:body}
}

```

## `efc` - export a functional component and props type

```typescriptreact
/**
 * ${1:name} props.
 */
export type ${1:name}Props = {
  ${2:props}
}

/**
 * ${1:name} component.
 */
export const ${1:name}: React.VFC<${1:name}Props> = (props) => {
  return (
    <>
      ${2:body}
    </>
  )
}

```

## `efcd` - export a functional component and props type with default values

```typescriptreact
/**
 * ${1:name} props.
 */
export type ${1:name}Props = {
  ${2:props}
}

/**
 * ${1:name} component.
 */
const ${1:name}: React.VFC<${1:name}Props> = (props) => {
  return (
    <>
      ${4:body}
    </>
  )
}

${1:name}.defaultProps = {
  ${3:defaultProps}
}

export {${1:name}}

```

## `enp` - export a next.js page

```typescriptreact
import { NextPage } from 'next'

/**
 * ${1:name} page.
 */
export const ${1:name}Page: NextPage = () => {
  return (
    <>
      <div>
        ${2:body}
      </div>
    </>
  )
}

export default ${1:name}Page

```

## `ena` - export a next.js app

```typescriptreact
import type { AppProps } from 'next/app'

function MyApp({ Component, pageProps }: AppProps): React.ReactElement {
  return (
    <>
      ${1:body}
      <Component {...pageProps} />
    </>
  )
}

export default MyApp

```

## `end` - export a next.js document

```typescriptreact
import Document, {
  Html,
  Head,
  Main,
  NextScript,
  DocumentInitialProps,
  DocumentContext,
} from 'next/document'

class MyDocument extends Document {
  static async getInitialProps(
    ctx: DocumentContext
  ): Promise<DocumentInitialProps> {
    const initialProps = await Document.getInitialProps(ctx)
    return { ...initialProps }
  }

  render(): JSX.Element {
    return (
      <Html>
        <Head></Head>
        <body>
          <Main />
          <NextScript />
        </body>
      </Html>
    )
  }
}

export default MyDocument

```

## `erc` - export a react context

```typescriptreact
import { createContext, useContext } from 'react'

/**
 * ${1:name}ContextData type.
 */
export type ${1:name}ContextData = {
  ${2:fields}
}

/**
 * default ${1:name}Context data.
 */
export const default${1:name}ContextData: ${1:name}ContextData = {
  ${3:defaults}
}

/**
 * ${1:name}tContext.
 */
export const ${1:name}Context = createContext<${1:name}ContextData>(default${1:name}ContextData)

/**
 * ${1:name}Provider.
 */
export const ${1:name}Provider = ${1:name}Context.Provider

/**
 * ${1:name}Consumer.
 */
export const ${1:name}Consumer = ${1:name}Context.Consumer

/**
 * use ${1:name}Context.
 */
export const use${1:name}Context = (): ${1:name}ContextData => {
  return useContext(${1:name}Context)
}

```

## `ea` - export all from

generates `export * from ...`

```typescript typescriptreact
export * from ${1:source}

```
