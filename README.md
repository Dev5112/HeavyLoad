# HeavyLoad

HeavyLoad is a machine learning project aimed at predicting the transaction prices of heavy equipment and machinery based on their specifications and operational history. The dataset contains various technical, operational, and transactional parameters for each asset.

## How it Works

The goal of this project is to accurately predict the selling price (`TargetValue`) of heavy equipment using machine learning. By analyzing historical transactions, the project identifies key drivers of equipment value—such as its age, usage (e.g., operational hours), location, and specific technical features. 

This predictive capability can empower businesses to make informed pricing, purchasing, and sales decisions. The model achieves this by learning patterns from the training dataset and applying them to predict prices for new, unseen assets.

## Project Pipeline

The machine learning workflow implemented in the Jupyter Notebook follows these key steps:

1. **Import Libraries & Load Dataset**: Setting up the environment and loading training/testing data.
2. **Exploratory Data Analysis (EDA)**: Understanding data distributions, missing values, and target variable skewness (applying logarithmic transformation to stabilize variance).
3. **Data Preprocessing & Feature Engineering**: Cleaning data, handling missing values, and extracting new meaningful features from the existing parameters.
4. **Train-Validation Split**: Dividing the training data to evaluate model performance locally.
5. **Categorical Encoding & Scaling**: Applying Target Encoding and Ordinal Encoding for categorical variables, and scaling numerical features.
6. **Hyperparameter Tuning**: Optimizing model parameters to achieve the best possible performance.
7. **Feature Importance Analysis**: Identifying which specifications and features most heavily influence the equipment's price.
8. **Model Training & Validation**: Training various advanced regression models (e.g., Linear Regression, Ridge, CatBoost, XGBoost, LightGBM, and Stacking Regressors).
9. **Performance Evaluation & Comparison**: Comparing models using metrics like Root Mean Squared Logarithmic Error (RMSLE) and R-squared.
10. **Final Submission**: Selecting the best performing model and generating predictions for the test dataset.

## Project Files

- **`train.csv`**: The training dataset, which includes the asset features and the target variable (`TargetValue`).
- **`test.csv`**: The test dataset used to generate predictions. It contains all features except the target variable.
- **`sample_submission.csv`**: A template showing the correct format for final model predictions (`TransactionID` and `TargetValue`).
- **`metadata.csv`**: A data dictionary containing descriptions of all variables in the dataset.
- **`23f2000223-notebook-2026t2.ipynb`**: A Jupyter Notebook containing the data exploration, preprocessing, and model training code.

## Data Schema

The dataset consists of the following variables and their descriptions:

| Variable | Description |
| :--- | :--- |
| **TransactionID** | A unique serial number assigned to each individual accounting record. |
| **TargetValue** | The financial amount of the transaction, denominated in US Dollars. (Target Variable) |
| **AssetID** | The internal tracking number assigned to a specific piece of hardware. |
| **ProductConfigID** | A system-generated code representing the technical build-out of the unit. |
| **DataOriginCode** | A code indicating the specific software or platform where the data originated. |
| **VendorPartnerID** | The unique ID of the external entity or third-party provider involved. |
| **TransactionDate** | The official calendar date when the entry was finalized in the system. |
| **RegionCode** | The specific geographic area or legal jurisdiction where the event occurred. |
| **ManufactureYear** | The year the asset was originally produced. |
| **OperationalHoursMeter** | The lifetime total of active run-time or work cycles logged by the machine. |
| **UtilizationTier** | A ranking (Low, Medium, or High) based on how heavily the asset is used. |
| **Spec_FullDescriptor** | The complete alphanumeric string detailing all technical parameters. |
| **Spec_BaseClass** | The broad, primary category for the asset's technical specifications. |
| **Spec_SubClass** | A secondary, more specific tier within the technical classification. |
| **Spec_ReleaseSeries** | Information regarding the specific production run or version number. |
| **Spec_VariantModifier** | A code identifying specific revisions or custom tweaks to a standard model. |
| **FunctionalClassification** | A secondary grouping based on the asset's operational role. |
| **AssetScaleFactor** | A value representing the physical dimensions or capacity relative to a standard unit. |
| **InventoryGroupCategory** | The highest level of classification within the inventory system. |
| **InventoryGroupDescription** | A detailed text explanation of the primary inventory category. |
| **CabinType** | The specific design of the operator’s station and environmental enclosure. |
| **DrivetrainType** | The mechanical system used to transfer power to the movement components. |
| **Forks** | The specific attachment module used for lifting (Legacy terminology). |
| **col1** | The primary configuration of the drive system. |
| **col3** | The type of subsystem used for machine stabilization. |
| **col4** | The specific layout or reach of the extension arm. |
| **col5** | The status or type of the engine’s air intake/aspiration system. |
| **col6** | The current status or type of the primary extension module. |
| **col7** | The horizontal width of the active working component. |
| **col8** | Specifications regarding the machine's protective housing or shielding. |
| **col9** | The total rated power output (e.g., horsepower or kilowatts). |
| **col10** | The classification of the hydraulic or fluid-based power system. |
| **col11** | The type of interface used for load-bearing and shock absorption. |
| **col12** | Details on accessories designed for piercing or penetrating materials. |
| **col13** | Details on accessories used for finishing or smoothing surfaces. |
| **col14** | The logic and hardware used to control machine actuators. |
| **col15** | The external measurements of the wheels or tires. |
| **col16** | The type of mechanism used to couple or join different interfaces. |
| **col18** | The system used for traction and contact with the ground. |
| **col19** | The rate of fluid flow through the system by volume. |
| **col20** | The specific tread or surface pattern of the traction system. |
| **col21** | The width of the surface area that makes contact with the ground. |
| **col22** | The maximum reach or length of the operational arm. |
| **col23** | The design of the interface used to hold or retain materials. |
| **col24** | The configuration map for the machine’s control system logic. |
| **col25** | The specific profile or shape of the traction components. |
| **col27** | The specific design or category of the attached work tool. |
| **col28** | The configuration of the operator's directional steering inputs. |
| **col29** | The type of differential used for power distribution. |
| **col30** | The primary interface used by the operator for steering. |