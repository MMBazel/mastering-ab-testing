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
			 
			
		
Validity Tradeoffs: A Toy Algorithm

	https://www.kdd.org/kdd2017/papers/view/detecting-network-effects-randomizing-over-randomized-experiments
	https://content.linkedin.com/content/dam/engineering/site-assets/pdfs/ABTestingSocialNetwork_share.pdf
	

......
External Validity:
	We want to make sure there isn;t much overlap & we want to make sure they're representative of the geneal pop of linkedin
	
	

High Level Principles -
		
		
		Once we run algorithm based off of standard principles, we get really good results
		
		
		
Application:
		Application #1:
		The experiment was to try to get people to post more
			In this experiment:
				If just doing A/B test - would just see #1
				But with ego analysis, #2 - more positive results
						For some applications, it may be insist that you share/post more
						
						


		Application #2: 
		Had alogirthm change the recommendations that we did
			SHare more by sharing content your friends would like
			Resukt: 0 impact on kind of content beng shared
					Effect on alters - no change
					On egos - own viral actions inc. 
					
					
					
					
		Application #3:
		Redistributing attention 
				Make super influential people less visible (and the zeros more visible)
				
				
				
Practical Considerations:

	-Pick the righ concept of the graph 
	
	
	
A Simple Way to think about messaging experiments

		Messages are 1:1
		For any message we can say it was treated to treated, across buckets, etc
		
		Building Blocks of Model-
			Control - Control - like the same as if the treatment wasn;t hapening
			
			
			
		Cool Approximation 1/2: Corrected Lift
		
			Can add lift from messages sent by treatment and add the lift received from treatment group
			Can only d this if experiment is currently ranked at 50%
			
			The great thing is there is no cost - no need to do cluster - do regular condition and assuming messages are 1:1 (not broadcast)  
		


































