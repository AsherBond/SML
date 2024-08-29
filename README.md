# What is SML?
Semantic Modeling Language, or SML for short, encompasses over a decade of hands-on development, solving use cases for hundreds of customers across industries such as finance, healthcare, retail, manufacturing, CPG, and more. SML covers more than just tabular use cases. At its core, it is a multidimensional semantic modeling language that supports metrics, dimensions, hierarchies,  semi-additive measures, many-to-many relationships, cell-based expressions, and much more. 

SML delivers on the following requirements:

1. **Object-oriented**: SML is an object-oriented language that promotes composability and inheritance. This allows semantic objects to be shared within other semantic objects and across organizations, supporting easy and consistent model-building.
2. **Comprehensive**: SML is based on more than a decade of modeling experience across various industry verticals and use cases. SML handles multi-dimensional constructs and serves as a superset of all other existing semantic modeling languages.
3. **Familiar**: SML is based on YAML, a widely adopted, human-readable, industry-standard syntax.
CI/CD Friendly: SML is code, so it is compatible with Git and CI/CD practices for version control, automated deployment, and software lifecycle management. 
4. **Extensible**: SML syntax can be enhanced to support additional properties and features.
Open: SML is Apache open-sourced to support community innovation and is free to use in any application or use case.

## SML Example
The following is an example of an SML `model` object:

```unique_name: Internet Sales
object_type: model
label: Internet Sales
visible: true

relationships:
  - unique_name: factinternetsales_Date_Dimension_Order
    from:
      dataset: factinternetsales
      join_columns:
        - orderdatekey
    to:
      dimension: Date Dimension
      level: DayMonth
    role_play: "Order {0}"

dimensions:
  - Color Dimension
  - Size Dimension
  - Style Dimension
  - Weight

metrics:
  - unique_name: orderquantity
    folder: Sales Metrics

  - unique_name: salesamount
    folder: Sales Metrics
```

## SML Object Hierarchy
The following graphic illustrates the key SML objects and their relationships:

![SML Model Hierarchy](images/SML-Object-Hierarchy.png)


## SML Object Documentation

The following sections describe the different SML object types as well
as the properties available for each:

- [Catalog](sml-reference/catalog.md)
- [Package](sml-reference/package.md)
- [Calculations](sml-reference/calculations.md)
- [Connections](sml-reference/connections.md)
- [Datasets](sml-reference/datasets.md)
- [Dimensions](sml-reference/dimensions.md)
- [Metrics](sml-reference/metrics.md)
- [Models](sml-reference/models.md)
- [Row Security](sml-reference/row-security.md)

## What's in this repository?

Open-sourcing SML aims to promote the building of reusable models and semantic objects. We are making the SML specification available for public consumption and collaboration. Soon, we will add software tools to make serializations and translations from various semantic dialects easier.

We are or will be open-sourcing the following:

1. **A YAML-based Language Specification**: The SML specification is documented and encompasses tabular and multidimensional constructs.
2. **Pre-built Semantic Models**: The GitHub repository contains pre-built semantic models incorporating standard data models such as TPC-DS, common training models such as Worldwide Importers and AdventureWorks, and marketplace models such as Snowplow and CRISP. We expect to add semantic models for SaaS applications such as Salesforce, Google Analytics, and Jira soon.
3. **Helper Classes** *(coming soon)*: We will release helper classes that will facilitate the programmatic reading and writing of SML syntax.
4. **Semantic Translators** *(coming soon)*: We will release converters for migrating other semantic modeling languages to SML, including dbt Lab’s semantic layer and Power BI. Shortly, we expect to release a variety of converters to support the legacy (i.e., Microstrategy, Business Objects, Cognos) and modern (i.e. Looker) semantic modeling tools. 
