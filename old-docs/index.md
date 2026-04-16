# Home

## Introduction 

### What is the W4H Toolkit?

The W4H Toolkit provides an ecosystem of tools health researchers can use to collect, store, query and analyze wearable and EHR data.

### A Progressive Toolkit

W4H Toolkit is an ecosystem that covers most of the common features needed when using wearables in a clinical study or or trial. As studies can have very different requirements, W4H toolkit is designed to be flexible and incrementally adoptable. These are some of the use cases we currently support:

- Collect Fitbit and Garmin data
- Analyze compliance
- Transform the data, e.g., to compute energy expenditure
- Produce data reports for patients in a study
- Provide approximate queries, e.g., to query the HR of a cohort over an extended period of time
- Running your data science notebooks on Apache Spark
- Implementing data workflows using the library to simplify how you interact with wearable data.

Some of these use cases are provided both in notebooks and in dashboard.

## Quick Start

The best way to try the toolkit is to use the Docker container by following the [Quick Start](quick-start.md) that will get you up and running with the dashboard and some sample notebooks in less than 20 minutes.

## Components

The toolkit includes the following components:

- [Dashboard](dashboard/index.md): provides data input forms and visual analytics.
- [Notebooks](notebooks/index.md): is a collection of sample notebooks that demonstrate include Panda and Spark notebooks.
- [w4h-datasets](notebooks/): is a collection of datasets used in the W4H examples.
- [Postgres Extensions](): provides useful extensions to queries data in the W4H database.
- [Library](w4h-core): core python library of high-level commands to simplify how users interact with wearable data, making the platform more accessible and user-friendly.

## Best Practices

### Production Deployment

## Extra Topics

### Extending the Dashboard

### Using your own Postgres Database

### Contributing
