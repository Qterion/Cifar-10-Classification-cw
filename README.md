Model:

Backbone

My backbone consists of 2 types of blocks.

Block V1

![image](https://github.com/Qterion/Cifar-10-Classification-cw/assets/60145661/6aaadcf8-f369-4149-8a97-bf4759423aec)
 
A is computed by average pooling X then applying linear function to the output and activate the result with ReLu.
Each conv block contains convolutional, layer batch norm, activation, and dropout.

The output of a and convolutions is then multiplied by each other and summed.

Block V2

![image](https://github.com/Qterion/Cifar-10-Classification-cw/assets/60145661/8b314564-19b0-4c32-bbf6-68ea4794930a)


It’s pretty much the same block but each convolutional block goes through the convolutional cycle twice.

Afterwards the output value again average pooled and putted in classifier block which is in my case is basic linear function.

My final Architecture:

![image](https://github.com/Qterion/Cifar-10-Classification-cw/assets/60145661/69031ad8-9367-4acd-b622-ce2a9bb58c3c)

 
It consists of 1 block of version1 and 3 version2 blocks and then the output from them is sent to the classifier.
With these parameters I used for testing:

Batch_size=100

![image](https://github.com/Qterion/Cifar-10-Classification-cw/assets/60145661/dee14c18-9940-4a69-8d2d-7925c10275c8)
 
I was able to achieve highest Validation Accuracy of 88.92%

![image](https://github.com/Qterion/Cifar-10-Classification-cw/assets/60145661/4d8ef2a8-cc08-40bb-92c6-194659e1de27)


And here are the graphs for the Loss and train and validation accuracy.

![image](https://github.com/Qterion/Cifar-10-Classification-cw/assets/60145661/ced52de7-d17b-4462-9f30-539a738438e1)



By looking at the curve of validation we can clearly see that the model is a bit overfitted and could be improved, which might be achieved by decreasing learning rate or increasing the number of k’s.
