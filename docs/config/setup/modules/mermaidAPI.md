> **Warning**
>
> ## THIS IS AN AUTOGENERATED FILE. DO NOT EDIT.
>
> ## Please edit the corresponding file in [/packages/mermaid/src/docs/config/setup/modules/mermaidAPI.md](../../../../packages/mermaid/src/docs/config/setup/modules/mermaidAPI.md).

# Module: mermaidAPI

## Interfaces

- [ParseOptions](../interfaces/mermaidAPI.ParseOptions.md)
- [RenderResult](../interfaces/mermaidAPI.RenderResult.md)

## References

### default

Renames and re-exports [mermaidAPI](mermaidAPI.md#mermaidapi)

## Type Aliases

### D3Element

Ƭ **D3Element**: `any`

#### Defined in

[mermaidAPI.ts:75](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L75)

## Variables

### mermaidAPI

• `Const` **mermaidAPI**: `Readonly`<{ `defaultConfig`: `MermaidConfig` = configApi.defaultConfig; `getConfig`: () => `MermaidConfig` = configApi.getConfig; `getSiteConfig`: () => `MermaidConfig` = configApi.getSiteConfig; `globalReset`: () => `void` ; `initialize`: (`options`: `MermaidConfig`) => `void` ; `parse`: (`text`: `string`, `parseOptions?`: [`ParseOptions`](../interfaces/mermaidAPI.ParseOptions.md)) => `Promise`<`boolean` | `void`> ; `parseDirective`: (`p`: `any`, `statement`: `string`, `context`: `string`, `type`: `string`) => `void` ; `render`: (`id`: `string`, `text`: `string`, `svgContainingElement?`: `Element`) => `Promise`<[`RenderResult`](../interfaces/mermaidAPI.RenderResult.md)> ; `reset`: () => `void` ; `setConfig`: (`conf`: `MermaidConfig`) => `MermaidConfig` = configApi.setConfig; `updateSiteConfig`: (`conf`: `MermaidConfig`) => `MermaidConfig` = configApi.updateSiteConfig }>

## mermaidAPI configuration defaults

```ts
const config = {
  theme: 'default',
  logLevel: 'fatal',
  securityLevel: 'strict',
  startOnLoad: true,
  arrowMarkerAbsolute: false,

  er: {
    diagramPadding: 20,
    layoutDirection: 'TB',
    minEntityWidth: 100,
    minEntityHeight: 75,
    entityPadding: 15,
    stroke: 'gray',
    fill: 'honeydew',
    fontSize: 12,
    useMaxWidth: true,
  },
  flowchart: {
    diagramPadding: 8,
    htmlLabels: true,
    curve: 'basis',
  },
  sequence: {
    diagramMarginX: 50,
    diagramMarginY: 10,
    actorMargin: 50,
    width: 150,
    height: 65,
    boxMargin: 10,
    boxTextMargin: 5,
    noteMargin: 10,
    messageMargin: 35,
    messageAlign: 'center',
    mirrorActors: true,
    bottomMarginAdj: 1,
    useMaxWidth: true,
    rightAngles: false,
    showSequenceNumbers: false,
  },
  gantt: {
    titleTopMargin: 25,
    barHeight: 20,
    barGap: 4,
    topPadding: 50,
    leftPadding: 75,
    gridLineStartPadding: 35,
    fontSize: 11,
    fontFamily: '"Open Sans", sans-serif',
    numberSectionStyles: 4,
    axisFormat: '%Y-%m-%d',
    topAxis: false,
  },
};
mermaid.initialize(config);
```

#### Defined in

[mermaidAPI.ts:668](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L668)

## Functions

### appendDivSvgG

▸ **appendDivSvgG**(`parentRoot`, `id`, `enclosingDivId`, `divStyle?`, `svgXlink?`): `any`

Append an enclosing div, then svg, then g (group) to the d3 parentRoot. Set attributes.
Only set the style attribute on the enclosing div if divStyle is given.
Only set the xmlns:xlink attribute on svg if svgXlink is given.
Return the last node appended

#### Parameters

| Name             | Type     | Description                                      |
| :--------------- | :------- | :----------------------------------------------- |
| `parentRoot`     | `any`    | the d3 node to append things to                  |
| `id`             | `string` | the value to set the id attr to                  |
| `enclosingDivId` | `string` | the id to set the enclosing div to               |
| `divStyle?`      | `string` | if given, the style to set the enclosing div to  |
| `svgXlink?`      | `string` | if given, the link to set the new svg element to |

#### Returns

`any`

- returns the parentRoot that had nodes appended

#### Defined in

[mermaidAPI.ts:291](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L291)

---

### cleanUpSvgCode

▸ **cleanUpSvgCode**(`svgCode?`, `inSandboxMode`, `useArrowMarkerUrls`): `string`

Clean up svgCode. Do replacements needed

#### Parameters

| Name                 | Type      | Default value | Description                                                 |
| :------------------- | :-------- | :------------ | :---------------------------------------------------------- |
| `svgCode`            | `string`  | `''`          | the code to clean up                                        |
| `inSandboxMode`      | `boolean` | `undefined`   | security level                                              |
| `useArrowMarkerUrls` | `boolean` | `undefined`   | should arrow marker's use full urls? (vs. just the anchors) |

#### Returns

`string`

the cleaned up svgCode

#### Defined in

[mermaidAPI.ts:242](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L242)

---

### createCssStyles

▸ **createCssStyles**(`config`, `graphType`, `classDefs?`): `string`

Create the user styles

#### Parameters

| Name        | Type                                                                | Description                                                                                                               |
| :---------- | :------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------ |
| `config`    | `MermaidConfig`                                                     | configuration that has style and theme settings to use                                                                    |
| `graphType` | `string`                                                            | used for checking if classDefs should be applied                                                                          |
| `classDefs` | `undefined` \| `null` \| `Record`<`string`, `DiagramStyleClassDef`> | the classDefs in the diagram text. Might be null if none were defined. Usually is the result of a call to getClasses(...) |

#### Returns

`string`

the string with all the user styles

#### Defined in

[mermaidAPI.ts:171](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L171)

---

### createUserStyles

▸ **createUserStyles**(`config`, `graphType`, `classDefs`, `svgId`): `string`

#### Parameters

| Name        | Type                                       |
| :---------- | :----------------------------------------- |
| `config`    | `MermaidConfig`                            |
| `graphType` | `string`                                   |
| `classDefs` | `Record`<`string`, `DiagramStyleClassDef`> |
| `svgId`     | `string`                                   |

#### Returns

`string`

#### Defined in

[mermaidAPI.ts:219](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L219)

---

### cssImportantStyles

▸ **cssImportantStyles**(`cssClass`, `element`, `cssClasses?`): `string`

Create a CSS style that starts with the given class name, then the element,
with an enclosing block that has each of the cssClasses followed by !important;

#### Parameters

| Name         | Type        | Default value | Description                                    |
| :----------- | :---------- | :------------ | :--------------------------------------------- |
| `cssClass`   | `string`    | `undefined`   | CSS class name                                 |
| `element`    | `string`    | `undefined`   | CSS element                                    |
| `cssClasses` | `string`\[] | `[]`          | list of CSS styles to append after the element |

#### Returns

`string`

- the constructed string

#### Defined in

[mermaidAPI.ts:155](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L155)

---

### decodeEntities

▸ **decodeEntities**(`text`): `string`

#### Parameters

| Name   | Type     | Description        |
| :----- | :------- | :----------------- |
| `text` | `string` | text to be decoded |

#### Returns

`string`

#### Defined in

[mermaidAPI.ts:135](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L135)

---

### encodeEntities

▸ **encodeEntities**(`text`): `string`

#### Parameters

| Name   | Type     | Description        |
| :----- | :------- | :----------------- |
| `text` | `string` | text to be encoded |

#### Returns

`string`

#### Defined in

[mermaidAPI.ts:106](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L106)

---

### putIntoIFrame

▸ **putIntoIFrame**(`svgCode?`, `svgElement?`): `string`

Put the svgCode into an iFrame. Return the iFrame code

#### Parameters

| Name          | Type     | Default value | Description                                                                  |
| :------------ | :------- | :------------ | :--------------------------------------------------------------------------- |
| `svgCode`     | `string` | `''`          | the svg code to put inside the iFrame                                        |
| `svgElement?` | `any`    | `undefined`   | the d3 node that has the current svgElement so we can get the height from it |

#### Returns

`string`

- the code with the iFrame that now contains the svgCode
  TODO replace btoa(). Replace with buf.toString('base64')?

#### Defined in

[mermaidAPI.ts:270](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L270)

---

### removeExistingElements

▸ **removeExistingElements**(`doc`, `id`, `divId`, `iFrameId`): `void`

Remove any existing elements from the given document

#### Parameters

| Name       | Type       | Description                           |
| :--------- | :--------- | :------------------------------------ |
| `doc`      | `Document` | the document to removed elements from |
| `id`       | `string`   | id for any existing SVG element       |
| `divId`    | `string`   | -                                     |
| `iFrameId` | `string`   | -                                     |

#### Returns

`void`

#### Defined in

[mermaidAPI.ts:341](https://github.com/mermaid-js/mermaid/blob/master/packages/mermaid/src/mermaidAPI.ts#L341)