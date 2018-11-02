# mastering-ab-testing


Mastering Experimentation Workshop: LinkedIn 
10/26/2018
Experiment Science Team


Bojinov & Saint-Jacques
-Engineers on experiment sceince team

>>>>>>>>>> Part 1: A/B Testing + Cuasal Inference

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
		PYMK - People You May Know
			- Conditions of A/B test may be violated by interactions between the groups
			
		Testing for Network Effect
			Rather than doing individualized randomization
			But can do cluster-based arm
					Clusters, cliques, etc 
					So rather than flipping a coin per person, flip a coin per cluster 
					
					
		If you flip a coin per cluster vs person, you'll have less data (mayb 10-15K vs 40-80K) 
		Comparing Lift in BR & CBR (KDD)
		
		Procedure in Practice-
				-Will cluster and then decided treatment at strong cluster & then also individual and then compare 
		Results -- 
			-Feed difference
			-Did detect that there was a significant p-value for network effect and community detection
			
			
		If you recognize there is a huge network effect, can't use the normal
		
		LinkedIn ego-Clustering:
			-ego netwrok: me + people I know
			
		ego-Clustering Treatment Assignment - 
			Step 1- Me and all my professional connections will be in my network 
			
			Flip coin by cluster
				-If control cluster, willget new feature (but nnone friends)
				-If treatment cluster, will get features (and all my friends)
				
			Then compare just the egos of those cluster
			With this method, could get data of 200K clusters
			Then te final analysis is just a t-test
			 Everytime you increase level of connection, increases exponentionally (so best to just use first connection clusters)
			 
			
		
		

