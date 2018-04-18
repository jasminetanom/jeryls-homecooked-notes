# Pipelines in sklearn
Similar to orange, knime etc
Workflow

from sklearn.pipeline import Pipeline, make_pipeline

Use clean data

Pipeline of transforms with a final estimator.

Sequentially apply a list of transforms and a final estimator. Intermediate steps of the pipeline must be ‘transforms’, that is, they must implement fit and transform methods. The final estimator only needs to implement fit. The transformers in the pipeline can be cached using memory argument.


# Set params
change parameters