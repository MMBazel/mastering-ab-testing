# mastering-ab-testing


Mastering Experimentation Workshop: LinkedIn 
10/26/2018
Experiment Science Team


Bojinov & Saint-Jacques
-Engineers on experiment sceince team

>>>>>>>>>>>>>>>> Part 1: A/B Testing + Cuasal Inference
    -@LinkedIn: It's all automated, given them the first version of metrics we care about; specifically, what is the lift between old & new that they care about
    -p-Values: UNder null distrb, how likely to see result or more extreme (compare against specific null value)
							-Engineers might not always understand 

	>>>>>>>>>>>>	Causal Inference Beyond A/B testing - Observational Studies 
					For APP store, you can roll out APP upgrades -- app store won't always tell companies who has the new app; anyone who downloads the app for the first time, you'll immediately get the New App 
							-So even if running A/B Test, can be running a quasi A/B Test
							
							Observational Study - Don't control who gets the treatment (ex: systematic variations between treatment arms from people who've downloaded the app store)
							
							Sessions is a confounder 
							
							Observational Study- Since people choose, introduces systematic variation -- if want to extract causal estimate then must remove bias
							
							Important because A/B Tests can be infeasible - Example - Smoking - Observational study

							Common Support - 
									
							Propensity Score Methods -
											
											Observational study - we don't know the probability, because we gave that up
											If two people have the same propsenity score - computed as a function of variances - i.e. no longer systematic variation between yourswlf and someone else who has the same propensity score
											
											
							A/A Test: Important validation (see slide) 
									-Metrics before actual treatment assignment done - if passes, procedure able to extract the hidden randomized assigment
									
						
						Fixed Effects			
								Can isolate out time for the confounding effect
								We see people going in and out of control 
								See chart
								If ou just look at corr, looks like a huge effect
								Doubly robust (uses time snapshot)
								Fixed Effect - more believeable and inline with expectation and experiment
								Takeaway: Able to figure out which groups had the largest impact on contributing



>>>>>>>>>>>>>>>  Part 2: Network Effects



