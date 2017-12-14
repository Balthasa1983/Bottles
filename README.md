# Bottles

Summary: In this project, a VDD16 Neural Network is modified and trained to recognize the sorted / unsorted condition of our bottle store.

Action:

In order to keep the computational effort of the training as low as possible, we use a preloaded VGG16 network.
The 100 training images of the classes (good / bad) are used to determine and save the activations of the fc2 layer (FreaturizedPreSafe)
The last SoftMax layer is then learned against the activations of fc2. (FitFromFeaturized) and the entire model saved.
In the last step, the model is loaded (LoadBottleComputationGraph) and the images of the previously held test set are checked.
-> With this approach, we have achieved an accuracy of 94% - that was unfortunately too good to be true. In comparison with some newly created test dad we have come to only 64%. The assumption: The network may have been training for wrong features, as positive and negative data were created one after the other.

Procedure 2: The next training / test set was created by always creating two images with identical box constellations with additional badly placed bottles for the 'bad' set.

Work order:

FeaturizedPreSave - Precede activation of the last SChight for all images
FitFromFeaturized - Train the last shifts
LoadBottleComputationGraph - Apply the network to the TestSet
