# coughvid_audio_test
This is a deep learning final project. Original cough dataset: https://coughvid.epfl.ch/about/

The task is devide into three part: cough audio quality examination, covid/symptomatic/health detection and their visualization.

Data is first transformed into audio file and then be made into a spectrogram(122*199). The spectrogram has a fixed size. X-axis represents time (zero-padding to 10 seconds) and y-axis is the 256 frequency bins by applying short-time FFT (after downsampling to 24kHz). These data can be found:
