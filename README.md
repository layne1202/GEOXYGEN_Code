GEOXYGEN-code/
├─ README.md              # Main documentation (this file)
├─ requirements.txt       # Python dependencies
├─ LICENSE                # Project license (optional, e.g. MIT)
├─ .gitignore             # Ignore temporary/model/large files
└─ src/
    ├─ 1.Source.ipynb      
    ├─ 2.QC.ipynb      
    ├─ 3.Grid&Zone0&SOM.ipynb  
    ├─ 4.TimeSpaceFeature.ipynb 
    ├─ 5.Auxiliary_variable.ipynb   
    ├─ 6.RandomStratified.ipynb   
    └─ 7.Train&Predict&Dataset.ipynb 


Input file formats

1. Training CSV files (used by train_geoxygen_catboost.py)

For each depth D in depthlist, the training script expects a CSV file:

ROOT_DIR/<D>dbar/depth<D>_TRAIN.csv

For example, for depth = "100" and ROOT_DIR = /data/xxxx/Result_Data/alldoxy:

/data/xxxx/Result_Data/alldoxy/100dbar/depth100_TRAIN.csv



2. Prediction CSV files (used by predict_geoxygen_catboost.py)

The prediction script reads gridded or seasonal input CSVs and applies the
trained per-depth, per-zone models to reconstruct DO on the target grid.

For each depth D in DEPTH_LIST, and for each season in ["Spring", "Summer", "Autumn", "Winter"], it expects files:

INPUT_ROOT/<D>dbar/depth<D>_<Season>_TRAIN.csv

Example for depth = "80" and INPUT_ROOT = /data/wang/Result_Data/allnodoxy:

/data/xxxx/Result_Data/allnodoxy/80dbar/depth80_Spring_TRAIN.csv
/data/xxxx/Result_Data/allnodoxy/80dbar/depth80_Summer_TRAIN.csv
/data/xxxx/Result_Data/allnodoxy/80dbar/depth80_Autumn_TRAIN.csv
/data/xxxx/Result_Data/allnodoxy/80dbar/depth80_Winter_TRAIN.csv