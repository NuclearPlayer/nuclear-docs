---
description: Guidelines for converting existing Javascript code to Typescript
---

# Converting to Typescript

This is a checklist of hard requirements for old code that's being conerted from Javascript to Typescript.

Change the file extensions from `.js` to `.tsx` or `.ts` as appropriate \(`.tsx` is for files containing JSX, so anything that has React markup\). The directory for a component needs to be named the same as the component itself.

### Conventions for components

* Place their main code in `index.tsx`, while the css need to be placed in `styles.scss` in the same directory. Inside the component folder, there can be sub-components which make up the component higher up in the directory structure. Sometimes it's fine to place other small components in the same file as the main component too.
* Remove proptypes if they exist, and replace them with a Typescript type. Name it `[component name]Props` and place it in the same file as the component.
* The component's type should be `React.FC<ComponentProps>` where `ComponentProps` is the type described above.
* Use `React.MouseEventHandler` for functions that handle clicks, etc.
* All existing plain strings should be passed down to components as props.
* Components in the `ui` package should have Storybook stories and snapshot tests created for them.

###  Conventions for containers

Containers follow the same conventions as components, with the following additions:

* Hooks for the container need to be placed in `hooks.ts` or `hooks.tsx`, unless they include functionality that can be reused. If that's the case, put that hook in `packages/app/app/hooks` in a file named like the hook itself.
* Do not use higher order components - prefer hooks.
* Avoid using CSS in containers.
* New containers and ones converted from Javascript need a test suite in a file named `[container name].test.tsx` in the same directory as the container itself. Look at the existing tests to find out how to write them. Typically it involves mounting the container and simulating user interactions. Snapshots for these tests need to be placed in a `__snapshot__`directory \(this is the default that Jest uses\).
* If the container uses forms, they should be placed in `forms.tsx` or `forms.ts`.
* Containers should also handle accessing localized strings through `react-i18next` and its `useTranslation` hook. If you prefer, you can also use the `Trans` component directly in the components, as long as they're not from the `ui` package.

