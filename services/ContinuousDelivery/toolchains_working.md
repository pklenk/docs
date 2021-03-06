---

copyright:
  years: 2016

---
 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Working with toolchains
{: #toolchains_getting_started}

Last updated: 17 November 2016
{: .last-updated}  

A *toolchain* is a set of tool integrations that support development, deployment, and operations tasks. The collective power of a toolchain is greater than the sum of its individual tool integrations.
{: shortdesc}

Toolchains are available in the Public and Dedicated environments on {{site.data.keyword.Bluemix}}. You can create a toolchain in two ways: use a template to create a toolchain or create a toolchain from an app. On {{site.data.keyword.Bluemix_notm}} Public, toolchains are available in the US South region only.

##Getting started with toolchains: Public
{: #getting_started_public}

Each toolchain is associated with a specific organization (org) and any user that is a member of that org can access its associated toolchains. Before you create a toolchain, make sure that you are working in the org where you want to create the toolchain. The org that you are currently working in is displayed in the menu bar. To switch to another org, click the org in the menu bar and then select the org that you want to switch to.

###Creating a toolchain from a template   
{: #creating_a_toolchain_from_a_template}

You can use a template as a starting point to [create a toolchain (Link opens in a new window)](https://console.ng.bluemix.net/devops/create){: new_window} that includes a specific set of tool integrations. Learn more about how to use the templates from the [IBM Bluemix Garage Method (Link opens in a new window)](https://www.ibm.com/devops/method/category/tools){:new_window}.

1. Log in to [{{site.data.keyword.Bluemix_notm}} (Link opens in a new window)](http://console.ng.bluemix.net){:new_window}. The {{site.data.keyword.Bluemix_notm}} Dashboard opens and shows an overview of the active {{site.data.keyword.Bluemix_notm}} space for your org.
1. From the hamburger menu, click **Services**, and then click **DevOps**.
1. On the DevOps dashboard, on the **Toolchains** page, click **Create a Toolchain**.
1. On the **Create a Toolchain** page, click a toolchain template.
1. Review the diagram of the toolchain that you are about to create. The diagram shows each tool integration in its lifecycle phase in the toolchain. The diagram in the following image is an example. When you create a toolchain, the diagram shows each tool integration that is part of the toolchain.
![Toolchain diagram](images/toolchain_diagram.png)

1. Review the default information for the toolchain settings. The toolchain's name identifies it in {{site.data.keyword.Bluemix_notm}}. If you want to use a different name, change the toolchain's name.  
1. In the Configurable Integrations section, select each tool integration that you want to configure for your toolchain. A few of the tool integrations do not require configuration. For information about configuring the tool integrations, see [Configuring tool integrations](/docs/services/ContinuousDelivery/toolchains_integrations.html){: new_window}.
1. Click **Create**.  Several steps run automatically to set up your toolchain:

 * The toolchain is created.
 * If you configured the Delivery Pipeline tool integration, the pipelines are created and triggered.
 * If you configured the Sauce Labs tool integration, Sauce Labs is set up to add jobs to the pipelines and run tests.
 * If you configured the PagerDuty tool integration, PagerDuty is set up to send alert notifications to the service that you specified.
 * If you configured the Slack tool integration, Slack is set up to send notifications about deployment status to the channel that you specified.
 * If you configured the GitHub tool integration, the sample GitHub repo is cloned into your GitHub account.


###Creating a toolchain from an app
{: #creating_a_toolchain_from_an_app}

You can create a toolchain from your app. The toolchain can support continuous development, deployment, monitoring, and more, and it is associated with your app. Each app can be associated with a toolchain. When you push changes to the toolchain's GitHub repo, the pipeline automatically builds and deploys the app.  

1. On your app's Overview page, on the Continuous Delivery tile, click **Enable**. Your app is configured for continuous delivery from a new GitHub repo that is populated with the app starter code.
1. On the toolchain creation page, review the diagram of the toolchain that you are about to create. The diagram shows each tool integration in its lifecycle phase in the toolchain.
1. Review the default information for the toolchain settings. The toolchain's name identifies it in {{site.data.keyword.Bluemix_notm}}. If you want to use a different name, change the toolchain's name.
1. In the Configurable Integrations section, select each tool integration that you want to configure for your toolchain. A few of the tool integrations do not require configuration. For information about configuring the tool integrations, see [Configuring tool integrations](/docs/services/ContinuousDelivery/toolchains_integrations.html){: new_window}.
1. Click **Create**.  Several steps run automatically to set up your toolchain:

 * The toolchain is created.
 * If you configured the Delivery Pipeline tool integration, the pipelines are created and triggered.
 * If you configured the Sauce Labs tool integration, Sauce Labs is set up to add jobs to the pipelines and run tests.
 * If you configured the PagerDuty tool integration, PagerDuty is set up to send alert notifications to the service that you specified.
 * If you configured the Slack tool integration, Slack is set up to send notifications about deployment status to the channel that you specified.
 * If you configured the GitHub tool integration, the sample GitHub repo is cloned into your GitHub account.


##Getting started with toolchains: Dedicated
{: #getting_started_dedicated}

Each toolchain is associated with a specific org and any user that is a member of that org can access its associated toolchains. Before you create a toolchain, click the **{{site.data.keyword.avatar}}** icon in the menu bar to open the Account and Support widget and view the org that you are working in. If that org is not the org where you want to create the toolchain, switch to another org.

###Creating a toolchain from a template   
{: #creating_a_toolchain_from_a_template_dedicated}

You can use a template as a starting point to create a toolchain that includes a specific set of tool integrations.

1. On the {{site.data.keyword.Bluemix_notm}} Dashboard, on the **DEVOPS** tab, click the add button (+) to create a toolchain.
1. On the **Create a Toolchain** page, click a toolchain template. 
1. Review the diagram of the toolchain that you are about to create. The diagram shows each tool integration in its lifecycle phase in the toolchain. The diagram in the following image is an example. When you create a toolchain, the diagram shows each tool integration that is part of the toolchain.
![Dedicated toolchain diagram](images/toolchain_dedicated_diagram.png)

1. Review the default information for the toolchain settings. The toolchain's name identifies it in {{site.data.keyword.Bluemix_notm}}. If you already have a toolchain with that name, or if you want to use a different name, change the toolchain's name.  
1. In the Configurable Integrations section, select each tool integration that you want to configure for your toolchain. A few tool integrations do not require configuration. For information about configuring the tool integrations, see [Configuring tool integrations](/docs/services/ContinuousDelivery/toolchains_integrations.html){: new_window}.
1. Click **Create**.  Several steps run automatically to set up your toolchain:

 * The toolchain is created.
 * If you configured the Delivery Pipeline tool integration, the pipelines are created and triggered.
 * If you configured the PagerDuty tool integration, PagerDuty is set up to send alert notifications to the service that you specified.
 * If you configured the Slack tool integration, Slack is set up to send notifications about deployment status to the channel that you specified.
 * If you configured the GitHub Enterprise tool integration, the sample GitHub Enterprise repo is cloned into your GitHub Enterprise account.


###Creating a toolchain from an app
{: #creating_a_toolchain_from_an_app_dedicated}

You can create a toolchain from your app. The toolchain can support continuous development, deployment, monitoring, and more, and it is associated with your app. Each app can be associated with a toolchain. When you push changes to the toolchain's GitHub Enterprise repo, the pipeline automatically builds and deploys the app.  

1. In the upper-right corner of your app's Overview page, click **Add Toolchain**. Your app is configured for continuous delivery from a new GitHub Enterprise repo that is populated with the app starter code.
1. On the toolchain creation page, review the diagram of the toolchain that you are about to create. The diagram shows each tool integration in its lifecycle phase in the toolchain.
1. Review the default information for the toolchain settings. The toolchain's name identifies it in {{site.data.keyword.Bluemix_notm}}. If you already have a toolchain with that name, or if you want to use a different name, change the toolchain's name.
1. In the Configurable Integrations section, select each tool integration that you want to configure for your toolchain. A few tool integrations do not require configuration. For information about configuring the tool integrations, see [Configuring tool integrations](/docs/services/ContinuousDelivery/toolchains_integrations.html){: new_window}.
1. Click **Create**.  Several steps run automatically to set up your toolchain:

 * The toolchain is created.
 * If you configured the Delivery Pipeline tool integration, the pipelines are created and triggered.
 * If you configured the PagerDuty tool integration, PagerDuty is set up to send alert notifications to the service that you specified.
 * If you configured the Slack tool integration, Slack is set up to send notifications about deployment status to the channel that you specified.
 * If you configured the GitHub Enterprise tool integration, the sample GitHub Enterprise repo is cloned into your GitHub Enterprise account.


##Viewing a toolchain
{: #viewing_a_toolchain}

After you configure the toolchain and its tool integrations, you can view a visual representation of the toolchain.

* If you use {{site.data.keyword.Bluemix_notm}} Public, on the DevOps dashboard, on the **Toolchains** page, click a toolchain to open its Overview page. Alternatively, on the app's Overview page, on the Continuous Delivery tile, click **View Toolchain**. Then, click **Overview**. 
   
* If you use {{site.data.keyword.Bluemix_notm}} Dedicated, on the Dashboard, on the **DEVOPS** tab, click the toolchain to open its Tool Integrations page. Alternatively, in the upper-right corner of the app's Overview page, click **View Toolchain**.

* To access a tool integration that is in your toolchain, click the tool's tile. 
 
 **Tip**: If you have more than one GitHub or GitHub Enterprise repo, you might have multiple tiles for the same tool integration because each repo is represented by its own tile.


# Related Links
{: #rellinks}

## Tutorials and Samples
{: #samples}

* [Create and use your first toolchain (Link opens in a new window)](https://www.ibm.com/devops/method/tutorials/tutorial_toolchain_flow){:new_window}
* [Create a custom toolchain (Link opens in a new window)](https://www.ibm.com/devops/method/tutorials/tutorial_toolchain_custom){:new_window}
* [Create an application with three microservices (Link opens in a new window)](https://www.ibm.com/devops/method/tutorials/tutorial_toolchain_microservices){:new_window}
* [Create a toolchain from a template on {{site.data.keyword.Bluemix_notm}} Dedicated (Beta) (Link opens in a new window)](https://www.ibm.com/devops/method/tutorials/tutorial_dedicated_toolchain_template_flow){:new_window}
* [Create a toolchain from an app on {{site.data.keyword.Bluemix_notm}} Dedicated (Beta) (Link opens in a new window)](https://www.ibm.com/devops/method/tutorials/tutorial_dedicated_toolchain_app_flow){:new_window}

## Related Links
{: #general}

* [Microservices toolchain (Link opens in a new window)](https://www.ibm.com/devops/method/toolchains/microservices_toolchain){:new_window}
* [Simple toolchain (Link opens in a new window)](https://www.ibm.com/devops/method/toolchains/simple_toolchain){:new_window}
* [IBM Bluemix Garage Method (Link opens in a new window)](https://www.ibm.com/devops/method){:new_window}
