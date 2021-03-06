# SCM Plugins

## About

SCM Plugins come in two flavors: `ScmExport` and `ScmImport`.

`ScmExport`
: Allows exporting Job changes.

`ScmImport`
: Allows importing Job changes.

The two types can be combined or used separately.

## Configuring

Each Project can enable a single `ScmImport` and/or `ScmExport` plugin.

This is done in the SCM Configuration page in the Rundeck GUI.

Alternately, you can use the [Rundeck API - SCM](/api/rundeck-api.md#scm).

SCM Configuration for a project is _not_ stored in the `project.properties`
configuration contents.

## Java Plugin Type

- _Note_: Refer to [Java Development](/developer/01-plugin-development.md#java-plugin-development) for information about developing a Java plugin for Rundeck.

The plugin interface is [ScmExportPluginFactory]({{{javaDocBase}}}/com/dtolabs/rundeck/plugins/scm/ScmExportPluginFactory.html).
This factory type should produce a [ScmExportPlugin][] object.

The plugin interface is [ScmImportPluginFactory]({{{javaDocBase}}}/com/dtolabs/rundeck/plugins/scm/ScmImportPluginFactory.html).
This factory type should produce a [ScmImportPlugin][] object.

[scmexportplugin]: {{{javaDocBase}}}/com/dtolabs/rundeck/plugins/scm/ScmExportPlugin.html
[scmimportplugin]: {{{javaDocBase}}}/com/dtolabs/rundeck/plugins/scm/ScmImportPlugin.html

## Localization

For the basics of plugin localization see: [Plugin Development - Plugin Localization](/developer/01-plugin-development.md#plugin-localization).

### Message Codes

In addition to the [basic plugin message codes](/developer/01-plugin-development.md#defining-plugin-localization-messages), SCM Plugins can have multiple "input views" with a set of properties,
as well as a set of "setup" properties.
The codes for these properties can be defined in your "messages.properties"
file using the following patterns:

- `setup.property.NAME.title` Title for setup property named "NAME"
- `setup.property.NAME.description` Description for setup property named "NAME"
- `action.ID.title` Title for action view with ID "ID"
- `action.ID.description` Description for action view with ID "ID"
- `action.ID.buttonTitle` Button Title for action view with ID "ID"
- `action.ID.property.NAME.title` Title for property named "NAME" for action view with ID "ID"
- `action.ID.property.NAME.description` Description for property named "NAME" for action view with ID "ID"

## Example

The Git Plugin bundled with rundeck provides an example.

View: [Git Plugin Source](https://github.com/rundeck/rundeck/tree/master/plugins/git-plugin).
