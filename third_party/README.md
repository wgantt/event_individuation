# Third-Party Code

This directory contains near- or exact copies of files taken from the [GTT model repo](https://github.com/xinyadu/gtt), used to produce the results in Table 2 of the paper. These files include:

- `eval.py`: the script used to compute CEAF-REE scores for all predictions in the `model_predictions/` directory.
- `docids_event_n.json`: a JSON file containing MUC-4 test set document IDs grouped by the number of events (templates) in their gold annotations. This is needed by `eval.py`, though it is not actually used to obtain any of the results in our paper.
