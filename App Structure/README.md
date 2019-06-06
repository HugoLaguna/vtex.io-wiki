# Getting Started

Let’s take a look at the generated files to understand this app’s structure. You can browse your code with any editor, but we strongly recommend using Visual Studio Code (VSCode).

The main file of any app is the `manifest.json`. It has important metadata about your apps, such as its vendor, name, version (we use strict semantic versioning), app dependencies, builders and policies.

Let's take a look at an example manifest file and all its properties:

```json
{
    "vendor": "vtex",
    "name": "store-theme",
    "version": "2.1.0",
    "builders": {
        "styles": "1.x",
        "store": "0.x"
    },
    "mustUpdateAt": "2020-06-06",
    "scripts": {
        "postreleasy": "vtex publish --verbose"
    },
    "dependencies": {
        "vtex.store": "2.x",
        "vtex.store-header": "2.x",
        "vtex.product-summary": "2.x",
        "vtex.store-footer": "2.x",
        "vtex.store-components": "3.x",
        "vtex.styleguide": "9.x",
        "vtex.slider": "0.x",
        "vtex.carousel": "2.x",
        "vtex.shelf": "1.x",
        "vtex.menu": "2.x",
        "vtex.minicart": "2.x",
        "vtex.product-details": "1.x",
        "vtex.product-kit": "1.x",
        "vtex.search-result": "3.x",
        "vtex.login": "2.x",
        "vtex.my-account": "1.x",
        "vtex.flex-layout": "0.x",
        "vtex.rich-text": "0.x",
        "vtex.store-drawer": "0.x",
        "vtex.locale-switcher": "0.x",
        "vtex.product-quantity": "1.x"
    },
    "$schema": "https://raw.githubusercontent.com/vtex/node-vtex-api/master/gen/manifest.schema",
    "title": "Store Theme",
    "description": "VTEX IO Store Theme",
    "registries": [
        "smartcheckout"
    ]
}
``` 
**Vendor**, **Name**, and **Version**: These three properties compose your **App Id**. Upon publishing an app, this is the immutable identifier to install and uninstall an app. For example, we could reference this app as `storecomponents.store-theme@0.1.0`

**Title** and **Description**: These will be used by administration interfaces such as My Apps admin.

**Builders**: Builders define which type of code or configuration you wish to export on this app. This app is using the Styles and Store builders, which affect, respectively, the visual theme and the layout structure of a store. There are multiple other builders for specific use cases, such as `react`, `messages`, `node`, `graphql`, etc. You can read more about builders, but for now, let's focus on these two.

**Dependencies**: Your app may depend on other apps so you can leverage existing functionality provided by them. Dependencies can either be *called at runtime* by your app, e.g. by depending on an app that exports a GraphQL schema, or they can be used to **dynamically import code** from another app. More on this later.