# AI Tool Specification

This is a spec and structure model for AI toolbox contents. Each element is documented with structured model specification, tool repository, and documentation template.

Types of tools:

- Library
- Supporting component
- AI product template
- AI product

## 1. AI Tool Specification

Common metadata for tools and its entities:

- **id** - fully qualified name, unique for the element. Necessary for the references.
- **name** - name of the solution
- **description** - detailed description of the solution (markdown)
- **version** - version of the solution
- **tags** - label the solution so that to be easily filtered and accessible
- **kind** - entity-specific category

### 1.1. AI-tool Specification

In general, AI tool as a composite software project containing one or more entities of different types.

Kinds:

- library
- product
- component
- template
- tool

Besides common metadata elements, the following spec elements are required

- **license**
  - **name**
  - **ref** (optional, relative or absolute URL)
- **problems** - list of problem tags describing what the tool addresses
- **ai** - AI domain (e.g., text, video, audio, …)
- **domain** - reference to the domain type (e.g., mobility, security, civil protection, …)
- **usage** - documentation (markdown) of the scenarios describing how the tool can be used in practice
- **howto** - list of HowTo scenarios describing the operations with the tool. Each howto is defined with
  - **title** - name of the howto
  - **description** - short description of the howto
  - **ref** - full documentation of the procedure (markdown)

Each AI tool may contain also the following entities

- **datasets** - list of data entity specs that the AI tool relies on
- **models** - ML model specs the tool defines or relies on
- **operations** - list of operations over the tool entities. This may include the exploration notebooks, deployment procedures, data processing jobs, model training, or the whole pipelines.
- **deployments** - list of deployable entities of the tool: AI services, data services, Web apps. 

### 1.2. Dataset Specification

Kinds (depend on data organization)

- table
- artifact
- ...

Besides common metadata elements, the following spec elements are allowed (optional)

- **schema** - definition of the dataset specification, if applies
  - **type** - format / organization of the schema (JSON Schema, Table Schema, AVRO, …)
  - **ref** - URL of the spec file (relative or absolute)
- **sample** - sample data
- **value** - dataset instance as URL (relative or absolute)

### 1.3. Model Specification

Kinds (depend on the format and framework)

- huggingface
- mlflow
- ...

Besides common metadata elements, the following spec elements are allowed (optional)

- **framework** - name of the library underlying the model
- **metrics** - metrics of the model specific to the type of the library
  - **type** - fully qualified metric ID
  - **value** - evaluated metric value
  - **name** - human-readable metric name
  - **args** - dictionary of parameters for the metric to be applied
- **parameters** - hyper parameters of the model as key-value pairs
- **value** - model instance as URL (relative or absolute)

### 1.4. Deployment Specification

Kinds:
- service
- webapp
- widget
- monitor
- ...

Besides common metadata elements, the following spec elements are allowed (optional)

- **implementation**
  - **framework** - deployment platform
  - **spec** - implementation specification (framework-specific)
- **openapi** - reference to OpenAPI spec if present


### 1.5. Operation Specification

Kinds:

- job
- deploy
- notebook
- pipeline
- ...

Besides common metadata elements, the following spec elements are foreseen

- **implementation**
  - **framework** - execution platform
  - **spec** - implementation specification (framework-specific)
- **task** - the task tag the operation characterizes (optional). For example,
  - For data: validate, transform
  - For models: train, evaluate, monitor, optimize, adapt, serve
  - For services: deploy, build
- **inputs** - references to the entities consumed by the operation
- **outputs** - references to the entities produced by the operation
