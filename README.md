# using_mask_rcnn
how to use mask_rcnn network to train your own datasets 

thanks to the project Mask_RCNN object detection
https://github.com/matterport/Mask_RCNN

the link above gives more details about the network.

//************How to setup mask rcnn************//
1.colone or download the Mask_RCNN
2.cd to the path where you saved the Mask_RCNN
3.cd ./Mask_RCNN_master  then run the setup.py
4.done

//************make you own datasets************//
there some different kind of datasets forms like CoCo, VIA and lableme（PNG form）。
i prefer VIA，the code in houseorpole is based on the 
VIA datasets. you can see the example in Mask_RCNN_master/samples/balloon.py
the balloon.py has only one class. if you want to detect more than one classes,  
change the config.NUM_CLASSES = 1+x(x = the number of object)
change the datasetclass 

