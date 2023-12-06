# Pang Jun Rong ID2223 Lab 2 Submission

## Testing UI (Task 1)
### Microphone/Upload Audio
If a microphone is not available on your device, you can change the following code in <code>inference-pipeline.ipynb</code> to use "test-audio.mp3":<br>
<i>inputs=gr.Audio(sources="microphone", type="filepath")</i><br>
to<br>
<i>inputs=gr.Audio(sources="upload", type="filepath")</i>

### TikTok Transcribing
You can use the following Swedish TikToks to observe how the model transcribes pre-recorded videos:
https://www.tiktok.com/@svenskamedanastasia/video/7170736029102591238?q=svenska&t=1701867819429

## Model-Centric Approach
### Hyperparameter Tuning
We should first try to tune the learning rate of the model. According to Jong Wook Kim, one of the authors of Whisper, a practical learning rate to consider while fine-tuning is a value that is 40x smaller than what has been used for pre-training, and linearly decay it to zero over the course of training.

### Model Architecture & Transfer Learning
We could explore the benefits of adding additional layers to the pre-trained model; i.e. appending more sequential layers to Whisper to increase the model performance. By modifying the model architecture and leveraging on transfer learning, a smaller dataset is needed to achieve the desired acceptable level of performance.

## Data-Centric Approach
### Data Sources
We could also identify new data sources that could be integrated into the training process. For instance, additional features that will help the model better identify nuances in the selected language of choice.

### Data Augmentation
By augmenting our data (in this case, creating additional data points based on a slightly distorted version of audio datasets), we can build a model that is more resilient against white noise or variances in our input audio during inference.

### Data Cleaning
In the dataset we used, some data points with many downvotes may reflect a bad audio sample which is included. We could remove these samples as part of preprocessing to ensure that our model learns the correct nuances in our selected language of choice.
