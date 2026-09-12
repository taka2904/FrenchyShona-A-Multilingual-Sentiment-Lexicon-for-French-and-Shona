FrenchyShona Part 2 Runtime Audit

train_seconds:
Wall-clock timing surrounding model fitting/fine-tuning in the
completed Part 2 run.

validation_inference_seconds:
Inference on the frozen 876-row validation partition for PLMs.

strict_test_inference_seconds:
Inference on the 1,224-row strict unseen test partition.

Ensembles and FrenchyShona hybrids reuse the saved component
probabilities. They do not involve additional model training.
Their probability-aggregation overhead was not treated as
independent model training time.

The successful Part 2 run used one visible Tesla T4 GPU.
The Kaggle T4 x2 allocation was deliberately restricted to
CUDA_VISIBLE_DEVICES=0 to preserve the fixed effective batch size.
