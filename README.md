Efficient Integration of Knowledge into Language Models

Class Project for DS-207: Introduction to NLP - [Report](https://indianinstituteofscience-my.sharepoint.com/:b:/g/personal/rameshgb_iisc_ac_in/EQcgMbzLsAtPq2b7O6RodPQBfuS0s4KyTVNSazrqCYtf-w?e=y68Se5)


Baselines:
1. Locating and Editing Factual Associations in GPT (ROME) - Checkpoints are stored in ns3_r0_gpt2-xl.zip, run_017.zip and run_038.zip. Extract them and put in results folder as per the instructions in results/readme
2. MQUAKE: Assessing Knowledge Editing in Language Models via Multi-Hop Questions (Mello model)
3. KnowledgeEditor(Editing Factual Knowledge in Language Models)- Datasets and checkpoints can be found here - [Datasets](https://indianinstituteofscience-my.sharepoint.com/:f:/g/personal/rkalyan_iisc_ac_in/EpsRYzGPbHxDsw0PGjSfhAQBRhhaFnsMeyODO3TzQ6pGmw?e=hfNqFo), Runs can be found here - [Runs](https://indianinstituteofscience-my.sharepoint.com/:f:/g/personal/rkalyan_iisc_ac_in/EvHZ5jghh9tItYZGUcIJt08BNQUhI2IlCB5-7zieX-6eqQ?e=55ybmf)


Knowledge Editor with Causal Tracing (KECT):
1. Causal tracing is done on the GPT model to localize the facts and the facts are updated similar to Knowledge Editor but more efficiently by updating only the weights corresponding to localized fact.
1. Checkpoints are stored in ns3_r0_gpt2-xl.zip, run_078.zip and run_085.zip. Extract them and put in results folder as per the instructions in results/readme
2. Detailed report and analysis - [Report](https://indianinstituteofscience-my.sharepoint.com/:b:/g/personal/rameshgb_iisc_ac_in/EXZ8Ymz1zztGsG_dStR3mMoBEdLATmBw5i0b2YHFj12W6Q?e=AFhsMY)

