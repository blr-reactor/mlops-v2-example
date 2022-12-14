# Demo Files Review

## Administration Setup - Created Workspace

1. https://github.com/blr-reactor/mlopsv2-sparse/blob/main/config-infra-prod.yml



## MLFlow

1. https://github.com/blr-reactor/mlopsv2-sparse/blob/main/data-science/src/train/train.py
```
    # log model hyperparameters
    mlflow.log_param("model", "RandomForestRegressor")
    mlflow.log_param("n_estimators", args.regressor__n_estimators)
    mlflow.log_param("bootstrap", args.regressor__bootstrap)
    mlflow.log_param("max_depth", args.regressor__max_depth)
    mlflow.log_param("max_features", args.regressor__max_features)
    mlflow.log_param("min_samples_leaf", args.regressor__min_samples_leaf)
    mlflow.log_param("min_samples_split", args.regressor__min_samples_split)
```

```
    # log model performance metrics
    mlflow.log_metric("train r2", r2)
    mlflow.log_metric("train mse", mse)
    mlflow.log_metric("train rmse", rmse)
    mlflow.log_metric("train mae", mae)
    
    mlflow.log_artifact("regression_results.png")
    
    mlflow.sklearn.save_model(sk_model=model, path=args.model_output)
```

2. https://github.com/blr-reactor/mlopsv2-sparse/blob/main/data-science/src/evaluate/test_evaluate.py

```
mlflow.sklearn.save_model(sk_model=model, path=model_input)
```


## Inner Loop - Create Pipeline - Prepare Data, Train, Evaluate, ResponsibleAI

1. https://github.com/blr-reactor/mlopsv2-sparse/actions/runs/3585372147
2. https://github.com/blr-reactor/mlopsv2-sparse/blob/main/mlops/azureml/train/pipeline.



## Deployment - Batch Endpoint and Realtime Inference

1.https://github.com/blr-reactor/mlopsv2-sparse/blob/main/mlops/devops-pipelines/deploy-online-endpoint-pipeline.yml
