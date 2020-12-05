# coughvid_audio_test
This is a deep learning final project. Original cough dataset: https://coughvid.epfl.ch/about/

The task is devide into three part: cough audio quality examination, covid/symptomatic/health detection and their visualization.

Data is first transformed into audio file and then be made into a spectrogram(122*199). The spectrogram has a fixed size. X-axis represents time (zero-padding to 10 seconds) and y-axis is the 256 frequency bins by applying short-time FFT (after downsampling to 24kHz). These data can be found:
After removing unwanted and missing features, the dataset is uploaded https://drive.google.com/drive/folders/14PRvpvlrUPDLt17ga1PpAPQvDOdqUA81?usp=sharing
Two examples are given.

The cough quality detection network is based on a supervised learning. The target is given in the original dataset. In this work, we divide the data into three groups: good(>0.6), intermediate(0.4-0.6), and bad(<0.4). The task is to detect whether or not a clear cough has been recorded. We use Resnet-18 to train the classification model. The accuracy is shown in the figure, using adam and sgd optimizer.

The covid detection is proved to be true using purely cough record. However, we use resnet-50 to train the model but it looks like random guess. The reasons may come froms the follows: 1. insufficient COVID example; 2. low record quality; 3. small spectrogram resolution; 4. insufficient network complexity.

Both two tasks above are classification problem. Confusion matrix and ROV curve are given to evaluate the result. 
