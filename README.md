# Email Demo Project
This is a proof of concept for email pages in AEM sent to Adobe Campaign.

This project uses modern practices for email creation including:

 * Editable Templates
 * Core Components
 * Repsonsive Grid

## Modules

The main parts of this project are:

* ui.apps: contains the /apps (and /etc) parts of the project, ie JS&CSS clientlibs, components, and templates
* ui.content: contains sample content using the components from the ui.apps
* ui.config: contains runmode specific OSGi configs for the project
* all: a single content package that embeds all of the compiled modules (bundles and content packages) including any vendor dependencies

## Connect AEM to Adobe Campaign Standard
https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html

## Connect AEM to Adobe Campaign Classic
https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html

## How to build

To build all the modules run in the project root directory the following command with Maven 3:

    mvn clean install

To build all the modules and deploy the `all` package to a local instance of AEM, run in the project root directory the following command:

    mvn clean install -PautoInstallSinglePackage

Or to deploy it to a publish instance, run

    mvn clean install -PautoInstallSinglePackagePublish

Or alternatively

    mvn clean install -PautoInstallSinglePackage -Daem.port=4503

Or to deploy only the bundle to the author, run

    mvn clean install -PautoInstallBundle

Or to deploy only a single content package, run in the sub-module directory (i.e `ui.apps`)

    mvn clean install -PautoInstallPackage

