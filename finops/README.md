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

Draft

## Tools

Draft

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
