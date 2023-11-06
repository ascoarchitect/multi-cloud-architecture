# FinOps

## Introduction

FinOps has always been an important foundation to deploying workloads into the cloud, however, with more organisations trying to derive better value from their cloud solutions this has now become a key focus. The Linux Foundation established a FinOps framework which addresses all of the cultural and process-based changes which need to be incorporated to ensure that it becomes part of your cloud DNA rather than a report which sits on a dashboard.

This resource will look to summarise some of the key components, but does not replace the need for more people becoming certified FinOps practitioners. You can find out more about the training and certification [here](https://learn.finops.org) and also in the further reading section below.

![Creative Commons License](https://licensebuttons.net/l/by/4.0/88x31.png "CC-By-4.0 License")

Used under license by [FinOps Foundation](https://www.finops.org)

## Common Misconceptions

FinOps is not about having the cheapest possible cloud bill.

Cheaper is not necessarily better.

One of the key messages that needs to be driven within an organisation is that FinOps is not about making everything cheaper and purchasing a huge number of reserved instances, committing to 1 or 3 year usage. Instead, it's about understanding the value that a service provides to the business, which could be the sale of a product or the generation of a lead for example. If a solution costs £80k per month to run in the cloud, but generates £400k of net new revenue for the organisation, then it's a fantastic investment. This could be defined as a value-based KPI in the form of a ratio where a minimum ratio of 1.5:1 revenue vs cost is positive but less is negative. In the example above, this would be a ratio of 5:1 which is positive.

The specific KPIs used are part of the discovery and deliverables that make up FinOps, but this demonstrates that when you just look at cloud as a cost rather than an enabler, you miss out the point of the exercise. Failing to grasp this could result in cost savings being made, but then leading to revenue impacts.

*"Unit economics and value-based metrics demonstrate business impact better than aggregate spend. Think of cloud as a driver of innovation, a driver of capability, and a way to get speed to market and customer satisfaction up."*

## FinOps Framework

<img src="https://github.com/ascoarchitect/multi-cloud-architecture/blob/main/finops/finops-framework.png" alt="FinOps Framework" style="height: 400px;"/>

The FinOps framework defines three phases which describe the maturity of an organisation's approach to FinOps. It's also highlighted that no single phase is necessarily better than anothwer, but instead should be catered for a situation. In the Run phase for example, you would expect an organisation to be utilising reserved instances (RI), savings plans or optimised spending when the project may be in the inception phase and exploring the use of serverless, where it's difficult to forecast the levels of compute or services required. Instead, you might take a crawl approach which allows the project to hone its focus on where it wants to get, but implement good principles which can be revised at a later time.

<img src="https://github.com/ascoarchitect/multi-cloud-architecture/blob/main/finops/finops-lifecycle.png" alt="FinOps Lifecycle" style="height: 300px;"/>

FinOps is an iterative process, much like Agile and DevOps where you gather data, analyse and enrich to provide information then make change decisions and implement, then gather more data on the effects of those changes. When you tie together the maturity phases with the lifecycle approach, your FinOps team, engineers and wider organisation will quickly improve its awareness of best practices and what works best. This will lead to more frequent and less individually impactful decisions as teams develop a 'muscle memory'.

### Principles

* Teams need to collaborate
* Decisions are driven by the business value of cloud
* Everyone takes ownership of their cloud usage
* FinOps reports should be accessible and timely
* A centralised team drives FinOps
* Take advantage of the variable cost model of the cloud

## It's All About Culture

When you are at the crawl phase of FinOps adoption, it will be likely that the FinOps team will be heavily involved with driving conversations and explaining some of the terms which are common across technology and finance. Some teams will ace understanding balance sheets, amortized costs and depreciation, and others will be masters at EC2 instance types, spot instances, auto-scaling groups and Grafana. It's important therefore to focus on establishing a common language which all teams can understand and relate to. This language should then be linked to busines value and outcomes so everyone can relate to the intention of FinOps and what it means to them.

Drawing out the backgrounds, experiences, motivations and biases from these various stakeholder groups will be important, so everyone knows the direction that is being taken and can gain support for filling any knowledge gaps where required.

Read more about FinOps and multi-cloud terminology via the links in the [further reading](./README.md#further-reading) section below.

## Personas

Working alongside the various stakeholder groups, or personas, in the business will be vital to ensure a successful cultual adoption of FinOps. The role of the FinOps practitioner is to act as the interface between the various groups and enable evidence-based decisions, leading to optimised cloud use and an increase in business value. **Everyone is responsible for their cloud usage**, therefore, providing these groups with the right information in a timely manner which supports their objectives is key.

Below is a list of the personas you can expect to interact with within an organisation:

* **Executives** - Roles such as Head of Cloud, CFO, CTO, CIO, Head of Infrastructure and others would fall into this category. They are all interested in maintaining a strategic competitive advantage, faster time-to-market and delivering innovative and market-leading products cost effectively. Each executive role will have varying challenges and key metrics, but FinOps will be a critical component for investment decisions, re-aligning budgeting for the cloud and managing risk amongst others.
* **Business/Product Owner** - This persona is primarily focussed on quickly bringing new products and features to the market and understanding how accurately the cloud costs can be forecasted, primarily to ensure they are able to determine unit cost economics and gross margins.
* **Engineering and Operations** - Engineers and Ops team members, such as Lead Software Engineers, Principal Systems Engineers, Cloud Architects, Service Delivery Managers, Engineering Managers, or Directors of Platform Engineering, focus on building and supporting services for the organisation. Cost is introduced as a metric in the same way that other performance metrics are tracked and monitored. Members of these teams consider the efficient design and use of resources via activities like rightsizing (the process of resizing cloud resources to better match the workload requirements), allocating container costs, finding unused storage and compute, and identifying whether spending anomalies are expected.
* **Finance** - Finance members, including Financial Planners, Financial Analysts, Financial Business Managers/Advisors, use the reporting provided by the FinOps team for cost allocation, showback allocation, and forecasting. They work closely with FinOps practitioners to understand historic billing data so that they can collaborate and build accurate forecasting models used for planning and budgeting.
* **Procurement** - Procurement Analysts, Sourcing analysts, Vendor Management or Directors within Procurement teams use insights provided by the FinOps team for identifying sourcing and purchasing of product and services within a Cloud Platform Vendor. Procurement should work closely with FinOps to ensure that prices and terms negotiated in the contract are fulfilled and streamline the procurement process. Procurement may have a legal component to review contract language.
* **IT Asset Manager** - IT Asset Manager, Software Asset Manager, IT Asset Analyst, IT Asset Administrator, IT Asset Specialist, IT Asset Compliance Manager, and IT Asset Procurement Specialist focus on maximizing the business value of all assets in the organization. It is also their responsibility to manage risk related to asset optimisation and contract compliance. They work closely with other IT professionals, including Architecture, Engineering and Security and stakeholders to develop and implement effective IT asset management strategies that align with the organisation's goals and objectives.
* **Sustainability Practitioner** - The Sustainability Practitioner within Enterprise IT works to integrate green initiatives and principles within the organization's IT operations. They drive strategies for energy-efficient and resource usage efficient practices, reduce emissions from IT infrastructure, and foster a culture of sustainable decision-making across procurement and operations. Balancing the demand for IT services and environmental goals, they leverage their expertise to reduce costs, manage risk, and introduce predictability in resource usage.

Read more about each FinOps persona and understand their individual objectives, challenges, key metrics and FinOps benefits [here](https://www.finops.org/framework/personas).

## Tagging and Reporting

To understand how your costs are attributed to projects and services, you need to use metadata to 'tag' or 'label' resources and accounts with information which can be used to drive your reports. Whilst the method fo achieving this will vary slightly between cloud providers, you will generally see these stored as 'key/value' pairs with each record. Tags can be applied at the resource, account and organisational level depending on the reporting requirements. For example, a resource might be tagged to identify the application ID or support contact for a database and an account might be the environment that it is being used for (e.g. development, production), or cost centre that will be billed.

This provides tremendous granularity for your cost allocation abilities where a single account may have a number of resources which are billed to different cost centres. For example, the database and data stores could be managed by one cost centre, security tooling by the information security team and underlying landing zone and networking by a shared services cost centre. These decisions are called business rules, and they determine how costs will be allocated based on tags and are generally held externally from the cloud provider.

Reporting is the central source of truth for FinOps and where many of the personas will interact with the information. By ingesting the data from your cloud provider(s) and analysing it centrally against your business rules, KPIs and forecasts, you're able to translate thousands or even millions of data points into meaningful dashboards and reports which can drive decisions. For all organisations, but specifically those in the walk and run phases, they should be ingesting data from their cloud providers using automation wherever possible to provide the ability for dashboards to be updated in near real-time.

## Tools

As the reader, I hope that you haven't just jumped down to this section to find a list of tools which will turnkey your organisation into FinOps legends - this simply won't happen. Whilst I'll recommend a couple of tools to look at, I can't emphasise enough the need to back up any tooling with the cultural changes required to implement the recommendations that would be provided. You need to understand why the recommendations are being made so you can determine whether they are in fact false positives or require action. Each workload needs to provide the context for the data which will allow each persona to understand which changes should be made - remember the lifecycle.

To assist with this, I would encourage you to firstly look at the native tools available in each of your cloud platforms in use to get a feel for the data which is generated. Next, you'll need to have tagged all your accounts and resources so it's much easer to group the data points together in your tool of choice.

<img src="https://github.com/ascoarchitect/multi-cloud-architecture/blob/main/finops/aws-cost-explorer.png" alt="AWS Cost Explorer" style="height: 400px;"/>

Using [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/) which is a free tool available on the AWS Console, you are able to filter all your costs using built-in categories and the tags which you have set on resources. This will allow you to quickly validate the costs for a set of resources by cost centre, environment, project or whatever is specific to your organisation. Getting your tagging agreed between the different personas then implemented before introducing any additional tools will allow you to understand the reports and recommendations which are generated.

<img src="https://github.com/ascoarchitect/multi-cloud-architecture/blob/main/finops/cloud-intelligence-dashboard.png" alt="Cloud Intelligence Dashboard" style="height: 400px;"/>

AWS Well-Architected Labs has a series of Cloud Intelligence dashboards which allow you to connect Grafana to your cost reporting data and gain instant insights across your organisation. Find out more here: https://www.wellarchitectedlabs.com/cloud-intelligence-dashboards/

|Tool|Details|
|---|---|
|Azure Cost Explorer|Available as a free tool for analysing your Azure Cloud costs, with a variety of analysis and filtering capabilities based on your tagging strategy. The tool provides forecasts based on historical and current usage to allow you to determine whether there are any trends which can be optimised.<br/>Find out more here: https://azure.microsoft.com/en-gb/products/cost-management.|
|Google Cloud Cost Management|Drive accountability for costs across your organisation, and better understand your return on cloud investments with flexible options for organising resources and allocating costs to departments and teams. Control your costs and reduce the risk of overspending with strong financial governance policies and permissions that make it easy to control who can do the spending and view costs. Stay smart about your spending with intelligent recommendations tailored to your business that help optimise usage, save time on management, and minimise costs.|
|Grafana|Grafana is a free and open-source platform which can be used for reporting data of all types. Built-in connectors are available for all popular cloud platforms allowing you to build your own visuals linked to organisational KPIs. Whilst this tool requires more up-front investment, unless you deploy pre-authored community and vendor dashboards, you can start off with simple visualisations then iterate as your team becomes more proficient. This tools also allows each persona to have access to the data for building out their own dashboards. The key benefit of using this platform is that is has a huge community and can also be used for visualising data from other sources outside of FinOps, making it a strategic reporting capability.<br/>Find out more here: https://grafana.com/grafana/|
|Apptio Cloudability|Cloudability brings financial accountability to the variable, consumption-based spending model of cloud. Allocation rules easily assign costs back to the business using the Business Mapping engine, ensuring an automated and complete chargeback. The platform provides a single-pane-of-glass, multi-cloud feature set that enables team ownership of spend via AI-backed anomaly detection, curated and customisable dashboards, budgets and forecasts, container analytics, and comprehensive optimisation recommendations. <br/>Find out more here: https://www.finops.org/members/apptio/|

This is not in any way a definitive list. Find out more about the selection of FinOps Certified Platforms here: https://www.finops.org/landscape/?prod_TOOLS_SERVICES%5BrefinementList%5D%5Bcertifications%5D%5B0%5D=FinOps%20Certified%20Platform

<img src="https://github.com/ascoarchitect/multi-cloud-architecture/blob/main/finops/finops-certified-platform.png" alt="FinOps Certified Platforms" style="height: 100px;"/>

## Further Reading

#### [FinOps Definition](https://github.com/finopsfoundation/definition)

This repository holds the canonical definitions, lifecycle, capabilities, etc for FinOps.

#### [FinOps Foundation](https://www.finops.org/)
The FinOps Foundation is the defacto resource for learning about FinOps with a rich blog and training materials for implementing the right FinOps mechanisms into your organisation. The FinOps Certified Practitioner course and certification prepares developers, leaders and executives with the best foundation for high quality code development and introducing the right cultural changes to support a successful cloud journey.

#### [FinOps Terminology](https://www.finops.org/resources/terminology/)
A list of terminology and examples for Cloud Cost Management, Public Cloud, Software Development & Operations, and Finance & Accounting categories.

#### [Multi-cloud Tools and Terminology](https://www.finops.org/wg/multi-cloud-tools-and-terminology/)
A matrix of tools available to help FinOps practitioners learn and practice efficient utilization of cloud resources as well as terminology and additional resources.

#### [Learning the Art of Cloud FinOps: Strategies, Tools, and Best Practices for Financial Success in the Cloud Era](https://amzn.to/40oaMEe)
Peter does a fantastic job of breaking down many of the fundamental elements of FinOps and how you can implement simple mechanisms into your organisation for cost optimisation, KPIs and reporting. 
