# obsstrat-photoclass-metric
LSST observation strategy evaluation with photo classification metric

- Generate SNIa light-curves with given observing strategy using Kyle Boone's notebook (based on LSST MAF framework). Modification allows to dump these simulations as a .csv file similar to PLAsTiCC challenge.



# Deprecated (already incorporated with SNN on the fly on sim_class_w_snn_maf.ipynb) _______ 
- If you want to obtain predictions
	- Clone SuperNNova https://github.com/supernnova/SuperNNova.git and setup environment

	- cd SuperNNova

	- Create database 
	``python run.py --dump_dir ../snndump --raw_dir ../test_sim_sncosmo --data --data_testing --list_filters u g r i z Y``

	- Get predictions with pre-trained model (output folder = dump_snn/models/vanilla_S_0_CLF_2_R_none_photometry_DF_1.0_N_global_lstm_32x2_0.05_128_True_mean_C)
	``python run.py --dump_dir ../snndump  --list_filters u g r i z Y --model_files ../pretrained_models/PLaSTiCC_20200327_vanilla_S_0_CLF_2_R_none_photometry_DF_1.0_N_global_lstm_32x2_0.05_128_True_mean_C/vanilla_S_0_CLF_2_R_none_photometry_DF_1.0_N_global_lstm_32x2_0.05_128_True_mean_C.pt --validate_rnn``

- Run inspection ``inspect_SNN_predictions.ipynb``