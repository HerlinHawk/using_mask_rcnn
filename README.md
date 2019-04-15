# using_mask_rcnn
how to use mask_rcnn network to train your own datasets 

thanks to the project Mask_RCNN object detection
https://github.com/matterport/Mask_RCNN

the link above gives more details about the network.

************How to setup mask rcnn************
1.colone or download the Mask_RCNN
2.cd to the path where you saved the Mask_RCNN
3.cd ./Mask_RCNN_master  then run the setup.py
4.done

************make you own datasets*************
there some different kind of datasets forms like CoCo, VIA and lableme
I made my datasets through VIA. After labling the data in the webside http://www.robots.ox.ac.uk/~vgg/software/via/, 
export the jason file(named via_region_data.jason), then put it into your train or val dataset
the file tree like this
---dataset
    ---train
        ---images
        ---via_region_data.jason(for train set)
    ---val
        ---images
        ---via_region_data.jason(for val set)
How to load the mask? if you have different oject classes to detect, you have to add class_ids in the code and rewrite the 
class number. The details will be shown in the code.you can also see the example in Mask_RCNN_master/samples/balloon.py
the balloon.py has only one class. if you want to detect more than one classes,  
change the config.NUM_CLASSES = 1+x(x = the number of object)

************Error I met**************
1.FilesError : no such files or directory ../..../
Using widows cmd to run the program, typing your dataset path in cmd then you may meet that error
just check the directory is right,you may type a wrong path
or to make it absulutly right you can add the code 
DEFAULT_DATA_PATH = ' ..\\..\\..\\...\\'(the dataset path)in windows system
the path's form is different from linux ,the oringal code is basaed on linux,so if we using windows
the path should be like the form above.

2.keyError : key 'name'  .......
the error happened in line 121 name = [r['region_attributes']['name'] for r in a['regions']]
why?
Because some images dont have a lable, it happened when you labled nothing in an image.
just add 'if 'name' in r[region_attributes]' following 'a['region']'

3.


