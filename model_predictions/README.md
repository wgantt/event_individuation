# Template Filling Model Predictions

This directory contains JSON-formatted template predictions on the MUC-4 test set for three recent template filling models: IterX ([Chen et al., 2023](https://aclanthology.org/2023.eacl-main.136/)), GTT ([Du et al., 2021](https://aclanthology.org/2021.naacl-main.70/)), and a slightly modified version of TempGen ([Huang et al., 2021](https://aclanthology.org/2021.naacl-main.69/)).

There are three kinds of prediction files:
- `*_preds.json`: contains the predictions in the native output formats of the associated model. These formats are different across the three models.
- `*_preds_converted.json`: contains the predictions after conversion to the format used by GTT. This was done to enable CEAF-REE scoring using the `eval.py` script from the [GTT code base](https://github.com/xinyadu/gtt) (included in this repo under the `third_party/` directory). Note that there is no `*_preds_converted.json` file for GTT predictions, since these would be identical to the unconverted file (`gtt_preds.json`).
- `*_pred_collapsed.json`: contains the same GTT-formatted predictions as the `*_preds_converted.json` files, but where template instances have been merged ("collapsed") into a single template per document, per type.

Additionally, we also include the "collapsed" version of the gold template annotations in `collapsed_gold_preds.json`. These files are used to compute the MUC-4 results in Table 2. All results can be obtained by running the following command from the project root:

```
python third_party/eval.py --pred_file model_predictions/<predictions_file> --gold_file data/test.jsonl
``` 

This will print results like the ones below (computed using `iterx_preds_converted.json` as the predictions file):

```
================= incident_type =================
P: 79.47%,  R: 59.70%, F1: 68.18%
================= PerpInd =================
P: 49.67%,  R: 38.60%, F1: 43.44%
================= PerpOrg =================
P: 57.78%,  R: 28.57%, F1: 38.24%
================= Target =================
P: 55.56%,  R: 41.50%, F1: 47.51%
================= Victim =================
P: 58.70%,  R: 54.00%, F1: 56.25%
================= Weapon =================
P: 62.34%,  R: 65.67%, F1: 63.96%
***************** micro_avg *****************
P: 60.92%,  R: 46.92%, F1: 53.01%
print: 79.47 59.70 68.18 49.67 38.60 43.44 57.78 28.57 38.24 55.56 41.50 47.51 58.70 54.00 56.25 62.34 65.67 63.96 60.92 46.92 53.01
```

All "Combined Score" results for MUC-4 in Table 2 of the paper report the "micro\_avg" F1 score above. The "Combined Score (original)" results are based on using the `preds_converted.json` files as the prediction files, while the "Combined Score (collapsed)" results are based on using the `preds_collapsed.json` files. The template type precision, recall, and F1 scores reported in the same table are to be read from the results for "incident\_type" above.
