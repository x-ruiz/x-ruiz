<p align="center">
  <img src="assets/banner.svg" alt="Xavier Ruiz — Data Engineer" width="100%"/>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/x-ruiz/"><img src="https://img.shields.io/badge/LinkedIn-x--ruiz-7C3AED?style=flat-square&logo=linkedin&logoColor=white&labelColor=18181B" alt="LinkedIn"/></a>
  <img src="https://img.shields.io/badge/Focus-Data%20Engineering-7C3AED?style=flat-square&labelColor=18181B" alt="Focus: Data Engineering"/>
  <img src="https://img.shields.io/badge/Clouds-GCP%20%7C%20AWS-52525B?style=flat-square&labelColor=18181B" alt="Clouds: GCP and AWS"/>
</p>

Data engineer focused on **lakehouse architectures, streaming & batch pipelines, and cloud data platforms** on GCP and AWS.

**Currently working on:** a cloud-agnostic Apache Iceberg lakehouse SDK in Java, a GitOps-managed unified data platform on GCP, and AI agents built with Google ADK.

<p>
  <img src="https://img.shields.io/badge/Java-18181B?style=flat-square&logo=openjdk&logoColor=A78BFA" alt="Java"/>
  <img src="https://img.shields.io/badge/Python-18181B?style=flat-square&logo=python&logoColor=A78BFA" alt="Python"/>
  <img src="https://img.shields.io/badge/Go-18181B?style=flat-square&logo=go&logoColor=A78BFA" alt="Go"/>
  <img src="https://img.shields.io/badge/SQL-18181B?style=flat-square&logo=postgresql&logoColor=A78BFA" alt="SQL"/>
  <img src="https://img.shields.io/badge/Apache%20Iceberg-18181B?style=flat-square&logo=apache&logoColor=A78BFA" alt="Apache Iceberg"/>
  <img src="https://img.shields.io/badge/Spark-18181B?style=flat-square&logo=apachespark&logoColor=A78BFA" alt="Spark"/>
  <img src="https://img.shields.io/badge/Kafka-18181B?style=flat-square&logo=apachekafka&logoColor=A78BFA" alt="Kafka"/>
  <img src="https://img.shields.io/badge/Flink-18181B?style=flat-square&logo=apacheflink&logoColor=A78BFA" alt="Flink"/>
  <img src="https://img.shields.io/badge/Airflow-18181B?style=flat-square&logo=apacheairflow&logoColor=A78BFA" alt="Airflow"/>
  <img src="https://img.shields.io/badge/Terraform%20%2F%20OpenTofu-18181B?style=flat-square&logo=terraform&logoColor=A78BFA" alt="Terraform / OpenTofu"/>
  <img src="https://img.shields.io/badge/GCP-18181B?style=flat-square&logo=googlecloud&logoColor=A78BFA" alt="GCP"/>
  <img src="https://img.shields.io/badge/AWS-18181B?style=flat-square&logo=amazonwebservices&logoColor=A78BFA" alt="AWS"/>
  <img src="https://img.shields.io/badge/Docker-18181B?style=flat-square&logo=docker&logoColor=A78BFA" alt="Docker"/>
</p>

<img src="assets/divider.svg" width="100%" alt=""/>

## How I Learn: The Mastery Framework

I organize my learning in **[obsidian-notes](https://github.com/x-ruiz/obsidian-notes)**, a knowledge base built around six engineering categories. Each category is split into focus areas that I use as note tags. Each one also has a *leadership lens*: alongside the technical skill, I think about how I'd guide a team through it.

| Category | Focus areas | Where it shows up in my repos |
|---|---|---|
| **Cloud Infrastructure** | Architecture design, IaC, containers, networking, cloud services | Unified data platform, Steam analytics platform, GCP env CLI, container from scratch |
| **Data Processing** | ETL/ELT, big data frameworks, storage, streaming, data quality | Lakehouse SDK, Premier League, F1, CTA tracker, Airflow ETL |
| **Information Security** | Secure coding, authN/Z, secrets management, threat modeling, compliance | KMS-encrypted state & keyless WIF auth in the unified data platform |
| **Software Engineering** | Design principles & patterns, testing, build & CI/CD | Lakehouse SDK (SPI plugins, Template Method), LeetCode |
| **System Resiliency** | Observability, fault tolerance, chaos engineering, incident response, DR | *Up next* |
| **AI Engineering** | ML pipelines, agent development, MLOps, ethical AI | ADK agents in playground-ai-engineering |

Notes and reading → hands-on experiments → real projects. The repos below are the hands-on part.

<img src="assets/divider.svg" width="100%" alt=""/>

## How My Repos Are Organized

Every repo name starts with a prefix that says what stage it's at:

| Prefix | Purpose |
|---|---|
| **`playground-*`** | **Where everything starts.** Incubator monorepos, one per discipline: data, cloud, and AI engineering. Here I prototype, write specs, take notes from books and courses, and iterate fast with no pressure to be "done." |
| **`project-*`** | **A self-contained build** with a clear goal and end-to-end scope. An idea graduates from a playground once it has a defined problem, a design, and enough substance to stand on its own. |
| **`platform-*`** | **Shared infrastructure.** Cloud platforms that other projects deploy onto and build on. They grow out of `playground-cloud-engineering`. |
| **`sdk-*`** | **Standalone libraries.** When a library built in a playground becomes stable enough to publish and version, it moves into its own `sdk-*` repo. |
| `tutorial-*` | Short, focused exercises for learning a single concept. |

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#18181B','primaryTextColor':'#F4F4F5','primaryBorderColor':'#7C3AED','lineColor':'#A1A1AA','fontFamily':'Helvetica, Arial, sans-serif','edgeLabelBackground':'#27272A'}}}%%
flowchart LR
    N["obsidian-notes<br/>study & plan"] --> P["playground-*<br/>prototype & iterate"]
    P -->|clear goal & scope| PR["project-*<br/>end-to-end build"]
    P -->|shared infrastructure| PL["platform-*<br/>cloud platforms"]
    P -->|reusable library| SDK["sdk-*<br/>versioned libraries"]
    PL -.->|hosts| PR
    SDK -.->|used by| PR
    SDK -.->|used by| PL
    PR -.->|lessons learned| N
    classDef hub fill:#7C3AED,stroke:#A78BFA,color:#FFFFFF;
    classDef grey fill:#27272A,stroke:#52525B,color:#E4E4E7;
    class P hub;
    class N grey;
```

Each project inside a playground is self-contained, with no imports across projects. That way it can be split out into its own repo, along with its CI workflows, when it's ready.

**Graduations in progress:**
- **`sdk_lakehouse` → `sdk-lakehouse`:** the [Lakehouse SDK](https://github.com/x-ruiz/playground-data-engineering/tree/main/maven_projects/sdk_lakehouse) is being developed through specs and iteration in `playground-data-engineering`. Its name already follows the `sdk-*` convention, so it keeps the same name when it moves out.
- **`platform_unified_data_gcp` → `platform-unified-data`:** a GCP unified data platform foundation being developed in `playground-cloud-engineering`.

<img src="assets/divider.svg" width="100%" alt=""/>

## Featured

### [Lakehouse SDK](https://github.com/x-ruiz/playground-data-engineering/tree/main/maven_projects/sdk_lakehouse) · *playground → sdk-lakehouse*
A multi-module **Java 17** SDK for declarative, GitOps-style management of Iceberg namespaces and tables. One pipeline codebase applies the same YAML definitions to local MinIO, an AWS Iceberg REST catalog, or **Google BigLake**. You switch targets by changing environment config and dropping in a cloud plugin JAR, which is loaded through a `ServiceLoader` SPI.
<br/><sub>Java 17 · Apache Iceberg 1.10 · Maven · Docker · AWS · GCP BigLake</sub>

### Unified Data Platform · *playground → platform-unified-data*
A GCP data platform foundation managed through GitOps. It covers org and seed-project bootstrap, KMS-encrypted remote state, and keyless GitHub Actions auth through Workload Identity Federation (with separate plan and apply identities). The platform is composed from tag-pinned Cloud Foundation Fabric modules, with thin Terragrunt wrappers for `dev`, `uat` and `prod`. Applies to `uat` and `prod` are gated.
<br/><sub>OpenTofu · Terragrunt · GitHub Actions · GCP · Cloud Foundation Fabric</sub>

### [playground-ai-engineering](https://github.com/x-ruiz/playground-ai-engineering)
A monorepo of custom agent skills and **Google ADK** agents. The main project is the *Obsidian Note Generator*: give it a YouTube video, a blog post, or a docs URL and it writes a structured note that follows my vault's conventions. In other words, an AI agent that feeds my learning system.
<br/><sub>Python · Google ADK · LLM agents</sub>

<img src="assets/divider.svg" width="100%" alt=""/>

## Playgrounds

| Repo | What's inside |
|---|---|
| [playground-data-engineering](https://github.com/x-ruiz/playground-data-engineering) | The Lakehouse SDK, a weather pipeline, and notes from *Spark: The Definitive Guide* and *Taming Big Data* |
| `playground-cloud-engineering` <sub>(private)</sub> | Infrastructure-as-code, GitOps patterns, and platform foundations, including the Unified Data Platform on GCP |
| [playground-ai-engineering](https://github.com/x-ruiz/playground-ai-engineering) | Google ADK agents and agent skills |

## Projects

### Data Engineering
| Project | What it does | Stack |
|---|---|---|
| [project-premier-league-analytics](https://github.com/x-ruiz/project-premier-league-analytics) | Ingests Premier League stats from a football API into GCS as Avro, transforms them into team and player tables, and serves a dashboard. Ingestion schedules are managed with Terraform. | Java, Avro, Jib, GCS, Terraform |
| [project-formula-1-wc-analytics](https://github.com/x-ruiz/project-formula-1-wc-analytics) | Historical F1 championship dashboards. Airflow ETL loads Kaggle data into GCS as Parquet and enriches it with city population data. Built for UChicago Applied Data Analytics. | Python, Airflow (Astro), Pandas, GCS, Parquet |
| [project-cta-tracker](https://github.com/x-ruiz/project-cta-tracker) | Streams real-time transit data: a Python producer publishes to Kafka and a Flink job consumes it. | Python, Kafka, Flink, Java |
| [project-market-data-airflow-etl](https://github.com/x-ruiz/project-market-data-airflow-etl) | Airflow DAGs that extract and process market data. | Python, Airflow |
| [project-apple-analysis](https://github.com/x-ruiz/project-apple-analysis) | An introductory extract → transform → load pipeline built with factory-pattern classes, run on Databricks. | Python, PySpark, Databricks |

### Cloud & Platform Engineering
| Project | What it does | Stack |
|---|---|---|
| [project-steam-analytics-platform](https://github.com/x-ruiz/project-steam-analytics-platform) | A Steam gaming analytics app with a Go (Gin) API, a React + Nivo charts frontend, and GCP infrastructure provisioned with Terraform. | Go, React, Terraform, GCP |
| [project-go-image-uploader](https://github.com/x-ruiz/project-go-image-uploader) | A containerized web app for uploading images to Google Cloud Storage. | Go, Gin, GCS, Docker |
| [cli-gcp-environment-configuration](https://github.com/x-ruiz/cli-gcp-environment-configuration) | A Python CLI that automates setting up a new GCP project environment. | Python, GCP |
| [backstage-ansible-awx](https://github.com/x-ruiz/backstage-ansible-awx) | A Backstage developer-portal plugin that integrates Ansible AWX. | TypeScript, Backstage |

## Tutorials & Learning

| Repo | What it covers |
|---|---|
| [obsidian-notes](https://github.com/x-ruiz/obsidian-notes) | The Mastery Framework knowledge base described above |
| [tutorial-go-container-from-scratch](https://github.com/x-ruiz/tutorial-go-container-from-scratch) | A minimal container runtime in Go, built from Linux namespaces, cgroups, and chroot |
| [tutorial-go-url-shortener](https://github.com/x-ruiz/tutorial-go-url-shortener) | A URL shortener HTTP service in Go |
| [tutorial-tf-website-bucket](https://github.com/x-ruiz/tutorial-tf-website-bucket) | Hosting a static website from a cloud bucket provisioned with Terraform |
| [tutorial-hadoop-word-count](https://github.com/x-ruiz/tutorial-hadoop-word-count) | The classic Hadoop MapReduce word count |
| [gcp-associate-cloud-engineer-course](https://github.com/x-ruiz/gcp-associate-cloud-engineer-course) | Course material and code for the GCP Associate Cloud Engineer certification |
| [leetcode](https://github.com/x-ruiz/leetcode) | Algorithm practice in Go |
| [resources](https://github.com/x-ruiz/resources) | Cheat sheets and reference links |

<details>
<summary><b>Sunset projects</b></summary>

- [project-ps5-trophy-tracker](https://github.com/x-ruiz/project-ps5-trophy-tracker): a proof of concept for a PlayStation trophy tracker (JavaScript, Cloud Functions). It was sunset because the unofficial PSN API's authentication broke.

</details>

<img src="assets/divider.svg" width="100%" alt=""/>

<p align="center">
  <a href="https://www.linkedin.com/in/x-ruiz/"><img src="https://img.shields.io/badge/Connect%20on%20LinkedIn-7C3AED?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"/></a>
</p>
