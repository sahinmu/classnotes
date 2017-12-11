```python
import scipy.io.wavfile, zipfile
import io, time
zip = '/home/burak/Downloads/goog_voice_train.zip'
with zipfile.ZipFile(zip, 'r') as z:
     wav = io.BytesIO(z.open('train/audio/off/09bcdc9d_nohash_1.wav').read())
     v = scipy.io.wavfile.read(wav)     
```

```python
import tensorflow as tf

init_op = tf.global_variables_initializer()

sample_rate = 16000.0

pcm = tf.placeholder(tf.float32, [None, None])

pcm2 = pcm[:,0:16000]

pcm3 = tf.reshape(pcm2, (-1,10,1600))

stfts = tf.contrib.signal.stft(pcm3, frame_length=1024, frame_step=256, fft_length=1024)

spectrograms = tf.abs(stfts)

num_spectrogram_bins = stfts.shape[-1].value
lower_edge_hertz, upper_edge_hertz, num_mel_bins = 80.0, 7600.0, 80
linear_to_mel_weight_matrix = tf.contrib.signal.linear_to_mel_weight_matrix(
  num_mel_bins, num_spectrogram_bins, sample_rate, lower_edge_hertz,
  upper_edge_hertz)
  
mel_spectrograms = tf.tensordot(spectrograms, linear_to_mel_weight_matrix, 1)
  
mel_spectrograms.set_shape(spectrograms.shape[:-1].concatenate(
  linear_to_mel_weight_matrix.shape[-1:]))

log_mel_spectrograms = tf.log(mel_spectrograms + 1e-6)

mfccs = tf.contrib.signal.mfccs_from_log_mel_spectrograms(log_mel_spectrograms)

mfccs2 = tf.reshape(mfccs, (-1, 30, 80))
```


```python
data = v[1].reshape((1,16000))
with tf.Session() as sess:
     sess.run(tf.global_variables_initializer())
     res = sess.run(mfccs2,feed_dict={pcm: data })
     print res.shape
```

```text
(1, 30, 80)
```






































