# QCDfake_Run2

# Compile postAnalyzers

./rootcom postAnalyzer_mc_QCDfake_phoNum analyze_mc_QCDfake_phoNum
./rootcom postAnalyzer_data_QCDfake analyze_data_QCDfake

# Run postAnalyzers to get data and MC distributions
./Datasub.sh
./MCsub.sh

# Gather distributions, perform template fits, compute the fake ratio and its systematics, and produce plots

hadd -f data_QCDfake_all.root data_QCDfake_*000*.root

root -l -q -b QCDfake_fakeratio_systematics_phopt.C

