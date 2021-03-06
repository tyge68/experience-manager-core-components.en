---
title: Developing Core Components
description: The Core Components provide robust and extensible base components which offer feature-rich capabilities, continuous delivery, component versioning, modern implementation, lean markup, and JSON export of content.
---

# Developing Core Components {#developing-core-components}

## Overview {#overview}

The Core Components provide robust and extensible base components, and their highlights are:

* Feature-rich capabilities
  * [Flexible configuration options](/help/get-started/authoring.md) to accommodate many use cases
  * [Pre-configurable capabilities](/help/get-started/authoring.md#pre-configuring-core-components) to define which features are available to page authors
* Continuous delivery
  * Frequent incremental functionality improvements
  * Availability of the [source code on GitHub](https://github.com/adobe/aem-core-wcm-components) to allow the developer community to give feedback and contribute
  * Installation through a [separately released content package](https://github.com/adobe/aem-core-wcm-components/releases) for component upgrades to be done independently from AEM upgrades
* [Component versioning](guidelines.md#component-versioning)
  * [Ensure compatibility within a version](#upgrade-of-core-components), yet allow the components to evolve
  * Allow multiple versions of one component to coexist on the same environment
* Modern implementation
  * Markup defined in [HTML Template Language](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) (HTL)
  * Content model logic implemented with [Sling Models](https://sling.apache.org/documentation/bundles/models.html)
* Lean markup
  * Following [Block Element Modifier](https://getbem.com/) (BEM) notation as of Release 2.0.0
    * Prior release follow [Bootstrap](https://getbootstrap.com/css/) naming conventions
  * Built around [accessibility guidelines](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)
  * Capable to be used for responsive and mobile sites
* Capability to serialize as JSON the content model for headless CMS use cases
* Accessible
  * Compliant with the [WCAG 2.0 AA standard](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

>[!CAUTION]
>
>Core Components require AEM 6.3 or later and Java 8 and and require the use of [editable templates](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
>
>Core Components do not work with the Classic UI nor with static templates.

## Gems Session Overview {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Gems on Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) is a series of technical deep dives delivered by Adobe experts. This series complements the product documentation and of all the other technical channels, allowing developers to get in touch and go deep on a specific topic.

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step-by-step tutorial.](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

## AEM Project Archetype {#aem-project-archetype}

[The AEM Project Archetype](/help/developing/archetype/overview.md) creates a minimal Adobe Experience Manager project as a starting point for your own projects, including an example of custom HTL components with SlingModels for the logic and proper implementation of the Core Components with the recommended proxy pattern.

## Delivered over GitHub {#delivered-over-github}

The Core Components are developed in and delivered through GitHub.

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-core-wcm-components project on GitHub](https://github.com/adobe/aem-core-wcm-components)
* Download the project as [a ZIP file](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

See the [Using Core Components](/help/get-started/using.md) documentation page to learn how to get started using them in your project.

Having the Core Components on GitHub will allow to do frequent updates, and to listen to the feedback from the AEM developer community. Also, this should help customers and partners to follow similar patterns when building custom components.

>[!NOTE]
>
>To keep up-to-date on the latest changes to the core components, you can watch the [Core Components repository](https://github.com/adobe/aem-core-wcm-components) on GitHub.

## Component Library

Check out the [Component Library](https://adobe.com/go/aem_cmp_library), which showcases the current release of the Core Components and gives examples of their usage.

### Core Components Out-of-the-Box {#out-of-the-box}

The core components may or may not be installed automatically depending on how you are running AEM.

#### AEM as a Cloud Service {#aem-cloud-service}

Although the Core Components are fully compatible with [AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html), the Core Components must be installed manually and are not available out-of-the-box.

#### AEM On-Premise {#on-premise}

In on-premise installations, the Core Components are visible in the Quickstart when the sample content is present, because the [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) uses them. However, when running in production (in `nosamplecontent` runmode, without sample content enabled), the core components won't be present anymore and must be installed on the AEM instance.

>[!NOTE]
>
>In on-premise production environments, always run the Quickstart in `nosamplecontent` runmode. To use the Core Components in `nosamplecontent` runmode, follow the instructions of the [Using Core Components](/help/get-started/using.md) documentation page.

## Technical Capabilities {#technical-capabilities}

The following table gives an overview of the differences between core components and foundation components.

For details about their authoring capabilities and options to pre-configurable them, [refer to the authoring page about them](/help/get-started/authoring.md).

| **Capability** |**Core Component** |**Foundation Component** |
|-----|---|---|
| Logic implementation |Java POJOs with [Sling Models](https://sling.apache.org/documentation/bundles/models.html) annotations |JSP code |
| Markup definition | [HTML Template Language](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html) (HTL) syntax |JSP code |
| XSS sanitization |Automated by HTL |Mostly manual  |
| CSS classes naming |Standardized naming convention based on [Block Element Modifier](https://getbem.com/) (BEM) notation (as of release 2.0.0) |Custom schemes |
| Dialog definition | [Coral 3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) |Coral 2 + Classic UI |
| JSON output | [Sling Models Exporter with Jackson serialization](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) |Default Sling servlet |
| Versioning | [For the model and the HTL](guidelines.md) |None |
| Testing |Unit Tests + Integration Tests |Integration Tests |
| Delivery | [Via public GitHub](https://github.com/adobe/aem-core-wcm-components) |Via Quickstart |
| License | [Apache License](https://www.apache.org/licenses/LICENSE-2.0) |Adobe proprietary |
| Contribution |Via pull request |Not possible |
| Accessibility |Fully compliant with the [WCAG 2.0 AA standard](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html |Only partially compliant with the [WCAG 2.0 AA standard](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## Component List {#component-list}

The following table lists the available Core Components, linking to their API, and indicates which foundation components they replace.

|Core Component|Description|Replaced Foundation Component(s)|
|---|---|---|
|[Page](https://adobe.com/go/aem_cmp_tech_page_v2)|Responsive page working with template editor|`/libs/foundation/components/page /libs/wcm/foundation/components/page`|
|[Breadcrumb](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)|Page hierarchy navigation|`/libs/foundation/components/breadcrumb`|
|[Title](https://adobe.com/go/aem_cmp_tech_title_v2)|H1-H6 title|`/libs/foundation/components/title /libs/wcm/foundation/components/title`|
|[Text](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text)|Rich text|`/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text`|
|[Image](https://adobe.com/go/aem_cmp_tech_image_v2)|Smart and lazy loading of optimal rendition size|`/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image`|
|[List](https://adobe.com/go/aem_cmp_tech_list_v2)|List of pages|`/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list`|
|[Social Media Sharing](https://adobe.com/go/aem_cmp_tech_sharing_v1)|Facebook and Pinterest sharing widget|`-`|
|[Form Container](https://adobe.com/go/aem_cmp_tech_form_container_v2)|Responsive form paragraph system|`/libs/foundation/components/form/start /libs/foundation/components/form/end`|
|[Form Text](https://adobe.com/go/aem_cmp_tech_form_text_v2)|Text input field|`/libs/foundation/components/form/text /libs/foundation/components/form/password`|
|[Form Options](https://adobe.com/go/aem_cmp_tech_form_options_v2)|Multiple options input field|`/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown`|
|[Form Hidden](https://adobe.com/go/aem_cmp_tech_form_hidden_v2)|Hidden input field|`/libs/foundation/components/form/hidden`|
|[Form Button](https://adobe.com/go/aem_cmp_tech_form_button_v2)|Submit or custom button|`/libs/foundation/components/form/submit`|
|[Navigation](https://adobe.com/go/aem_cmp_tech_navigation_v1)|A site navigation component that lists the nested page hierarchy|`/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav`|
|[Language Navigation](https://adobe.com/go/aem_cmp_tech_langnav_v1)|A language and country switcher that lists the global language structure|`-`|
|[Quick Search](https://adobe.com/go/aem_cmp_tech_search_v1)|A search component that displays the results as in-place suggestions in a drop-down menu|`/libs/foundation/components/search`|
|[Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1)|Allows the content author to easily create a teaser to further content using an image, title, or rich text and linking to further content or other actions|`-`|
|[Tabs](https://adobe.com/go/aem_cmp_tech_tabs_v1)|Allows the content author to organize page content within multiple tabs|`-`|
|[Carousel](https://adobe.com/go/aem_cmp_tech_carousel_v1)|Allows the content author to organize content in a rotating carousel of slides|`/libs/foundation/components/carousel`|
|[Content Fragment](https://adobe.com/go/aem_cmp_tech_cf_v1)|Allows for the display of a content fragment|`-`|
|[Content Fragment List](https://adobe.com/go/aem_cmp_tech_cflist_v1)|Allows for the display a list of content fragments|`-`|
|[Separator](https://adobe.com/go/aem_cmp_tech_separator_v1)|Separates content on a page|`-`|
|[Accordion](https://adobe.com/go/aem_cmp_tech_accordion_v1)|Organize content panels in a collapsible accordion|`-`|
|[Container](https://adobe.com/go/aem_cmp_tech_container_v1)|Organize components within a container|`-`|
|[Button](https://adobe.com/go/aem_cmp_tech_button_v1)|Create a button on a page|`-`|
|[Download](https://adobe.com/go/aem_cmp_tech_download_v1)|Add a downloadable asset to a page|`-`|
|[Experience Fragment](https://adobe.com/go/aem_cmp_tech_xf_v1)|Add an experience fragment to a page|`/libs/cq/experience-fragments/editor/components/experiencefragment`|
|[Embed](https://adobe.com/go/aem_cmp_tech_embed_v1)|Embed an external resource within a page|-|

### Upcoming Components {#upcoming-components}

For an overview of the upcoming Core Component road map see the [project wiki on GitHub](https://github.com/adobe/aem-core-wcm-components/wiki/home).

## Upgrade of Core Components {#upgrade-of-core-components}

One benefit of versioned components is that it allows to separate the migration to a new AEM version from the migration to new component versions. Also, if new component versions are available, it allows for the individual migration of each component to the new version.

Migrations to a new AEM version won't impact how the Core Components work, provided that their versions also support the new AEM version that is being migrated to. Customizations made to the Core Components should not be affected either, as long as they don't use APIs that have been [deprecated or removed](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html).

Migrations to new versions of the Core Components won't impact how the component works either, but new features might be introduced to page authors, which might require some configuration by a template editor, in case the default behavior isn't desired. Customizations however might need to be adapted, for more details see the [Customizing Core Components](customizing.md#upgrade-compatibility-of-customizations) page.

## When to Use the Core Components? {#when-to-use-the-core-components}

As the Core Components are all-new, and offer multiple benefits, it is recommended for new AEM projects to use them. For existing projects, a migration should be part of a larger project effort, for example a rebranding or overall refactoring.

Therefore, Adobe provides following recommendations:

* **New Projects**
  New projects should always attempt to use Core Components. If Core Components cannot be used directly or [extended](customizing.md) to satisfy project requirements, then create a custom component following the component architecture set forth in core components. Except where not otherwise possible, avoid using the [foundation components](#foundation-component-support).  
* **Existing Projects**
  Recommendation is keep using the [foundation components](#foundation-component-support), unless a site or component refactoring is planned.  
  As they are very widely used by most existing projects, the foundation components [will continue to be supported.](#foundation-component-support)
* **New Custom Components**
  Assess if an existing [Core Component may be customized](customizing.md).  
  If not, recommendation is to build a new custom component following the [Component Guidelines](guidelines.md).
* **Existing Custom Components**
  If your components work as expected, then keep them as they are.  
  If not, refer to "New Custom Components" above.

## Migrating to the Core Components

Any new project should be implemented with Core Components. However existing projects will usually have extensive implementations of the Foundation Components.

A larger effort on an existing project (for example a rebranding or overall refactoring) often offers a chance to migrate to the Core Components. To facilitate this migration, Adobe has provided a number of migration tools to encourage the adoption of the Core Components and the latest AEM technology.

[The AEM Modernization Tools](http://opensource.adobe.com/aem-modernize-tools/) allow for the easy conversion of:

* Static templates to editable templates
* Design configurations to policies
* Foundation Components to Core Components
* Classic UI to Touch-Enabled UI

For further information about the usage of these tools, [see their documentation](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>The AEM Modernize Tools are a community effort and are not supported or warrantied by Adobe.

## Core Component Support {#core-component-support}

Core Components are an integral part of AEM and supported as is, under the same terms and conditions as if they were delivered as part of the Quickstart.

Like other AEM product features, the general rule is: Components are first announced to be deprecated, and the earliest removed for the following AEM release. That gives customers at least one release cycle to move to the new version of the component, before dropping its support.

The version of each component clearly states the AEM versions that it supports. When support ceases for a version of AEM, then so does the support of the Core Components for that version of AEM.

For details about the support of component customizations, see the [Customizing Core Components](customizing.md) page.

## Foundation Component Support {#foundation-component-support}

Since the foundation components have served as a basis of so much project development over many AEM versions, they will continue to be supported into the foreseeable future.

However, Adobe's development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.

**Read next:**

* [Using Core Components](/help/get-started/using.md) - get up-and-running with Core Components in your own project.
* [Component Guidelines](guidelines.md) - to learn the implementation patterns of the Core Components.
