# MUC-4 Reannotation Study

This directory contains task materials, data, and analysis for the MUC-4 reannotation study presented in the paper:

- `muc_reannotation_task_materials.zip`: The complete task materials (including instructions) that were given to annotators in the reannotation study.
- `annotations`: The raw annotations (JSON-formatted, one file per annotator)
- `Reannotation Study Analysis.ipynb`: Jupyter notebook that computes interannotator agreement (IAA) for the study, as well as agreement statistics for model predictions. (See the notebook itself for further details.)
- `muc_agreement.csv`: A CSV with IAA statistics that is output by the notebook above.
- `muc_docs.csv`: A CSV listing the MUC-4 documents used in the study, together with the template type of the gold annotations for that document (all documents in the study featured templates of only a single type).