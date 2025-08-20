# Motivation

To see how the `mlflow` package can be used to autolog machine learning model parameters and metric results, store the outputs locally, and then view the "experiments" within the mlflow user interface via a local host.

This is to provide an alternative to using the mlflow integration on a platform such as Databricks or Microsoft Fabric.

# Usage

Install the project on your machine, set up a .venv with the required packages and then run the notebook.

To add more runs using different model types, you will first need to import the required modules (which may require installing the necessary packages first, if you are interested in using something like XGBoost or LightGBM). Then you need to create your own **empty** 'experiments' folder, where `mlflow`'s outputs will be stored.

Each new run for a different model needs to be created inside a `with` block (as demonstrated in the notebook). You define the `run_name` to make the run identifiable, and at the bottom of the block, you can give the model a name to make it identifiable i.e. in the line `mlflow.sklearn.log_model(lrg,'basic_logistic_regression')`, where `lrg` is the variable containing the instantiated model and `basic_logistic_regression` was the sensible human-readable name to be displayed in the mlflow user interface.

# The data

It comes from the publicly available NYC Taxi dataset, often used for machine learning practice. It has also been combined with latitude and longitude information corresponding to the zip codes in the original data. This comes from [here](https://public.opendatasoft.com/explore/dataset/georef-united-states-of-america-zc-point/table/).

# Contact

For technical assistance, please contact the [Specialist Analytics Team](mailto:scwcsu.analytics.specialist@nhs.net)