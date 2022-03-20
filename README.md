Task:		



To train a model over given dataset, which can efficiently detect objects :								
1> Person								
2> Car								
	
	
	
	
	
	
	
Dataset :



Images (jpg) , dynamic view of Humans and Cars 	





Ground Truth	:




COCO json	







										
Framework    :






Detectron2 : It is a platform for object detection. which provide all required support for fast training 								
										
										
										
										
Links to dataset and framework :





Detectron: 		https://github.com/facebookresearch/detectron2	



Metric Calculation		https://github.com/rafaelpadilla/Object-Detection-Metrics/tree/e3f29579afef10e8057bda1beb6154a3f354287c	









										
About the model	:






BackBone: 		




faster_rcnn_X_101_32x8d_FPN_3x			
ResNetXt												
cardinality : 32		
with FPN Trained for ~ 30 Epochs	



										

Train/Test Split :


https://github.com/akarazniewicz/cocosplit			

20% in Test set		







										
Primary Analysis.   :



No of   Class 	     :	2						
		
		
No of images	     : 	2239						
		
		
		
Class Label    : # Person	10800						
		  



 No of  Car	5972		
		 
		 
	 
No of  Missing Label:	0		
		
		
		
Some data exmaples are 	


			
1> very crowded	
			
			
			
2> scale of the object are varying
			
			
			
			
3> significantly occluded
			
			
			
			
4> in some cases not real word snap rather poster
			
			
			
										
										
										
Assumptions	:	


A deep backbone netwok will be better. choice to learn  better feature representation for the aforementioned chanllenges. (Case 1 and 2 )								
		
		
		
		
		
		
Keeping big warm up iterations will inhibit larger deviations slow paced learning  (Case 3,4 )	






										
Inference : 



Prediction results in directory : predictions	







										
Confusion Matrix	       		






					Predicted     Car	    Person
					
					
					
					
					
		       Actual            Car	        755	    151	
		       
		       
		       
		       
		       
		       
		                        Person	      1243    235						
										
										
										
Conclusion :    



Looking into metric, model is pretty confident with its prediction		



Recommendations	:     



We can still find that, some of the obvious object, but impacted by varying size. Hence need to work more critically on  FPN block. 								
		
		
		
		1> Add more layers to FPN 
		
		
		
		2> Or add more layer to Backbone network 								
										
										
										
