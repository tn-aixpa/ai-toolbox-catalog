# AI Tool Project Structure

To facilitate the documentation and reuse of the AI tools, it is expected that every tool is provided as 
a Git project that follows the common structure with thew following template:

- **README.md** - main documentation entry. Should have subsections briefly describing the tool, such as
  - AIPC tags (kind, ai domain, application domain)
  - description
  - usage
  - how to scenarios 
- **aipc.yaml** - product specification
- **data/** - folder with product artifacts (datasets, artifacts)
- **models/** - folder with model artifacts
- **src/** - folder with the source code of the operations
- **docs/** - folder with the documentation. May include
- **howto/** - list of markdown files with HowTo scenarios
- Other markdown documentation (e.g., usages, …)
