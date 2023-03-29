## Results of the competition

This is the results of other teams on the same dataset. Our primary objective was to to create 
model that meets the standards of the above mentioned models and takes less computational resources while training and prediction.


| Experiment  | Chest training size | Epochs | MAE |  Date |
| ------------- | ------------- | ------------- | ------------- |  ------------- |
| 16Bit challenge winner								| n/a	| 500	| 4.265	| 2017  |
| Radiologist	performance							| n/a	| n/a	| 7.32	| 2017  |
| Imagenet								| n/a	| 50	| 76.8	| 181020  |
| Imagenet								| n/a	| 250	| **8.8**	| 181029  |
| No TL, random init.					| n/a	| 250	| **10.8**	| 181030  |
| Chest 0-20yrs., 30 layers finetuning	| 1560	| 50	| 33.9	| 181022  |
| Chest 0-20yrs., 100 layers finetuning	| 1560	| 50	| 37	| 181022  |
| Chest 0-20yrs., 100 layers finetuning	| 1560	| 250	| 41.8	| 181024  |
| Chest 0-20yrs., 50 layers finetuning	| 1560	| 250	| 34.5	| 181025  |
| Chest 0-20yrs., 20 layers finetuning	| 1560	| 250	| 36.7	| 181026  |
| Chest 0-20yrs., 30 layers finetuning	| 1560	| 250	| 35.8	| 181027  |
| Chest 0-100yrs, 3 layers finetuning	| 89696	| 250	| 34.8	| 181103 |
| Chest 0-100yrs, all layers finetuning	| 89696	| 250	| pending*	| pending* |