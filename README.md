# **Intelligent Meeting Notes**

## **Project Description**

The **Intelligent Meeting Notes** Assistant aims to automate the generation of structured meeting summaries from audio recordings of city council meetings. This system seeks to streamline the meeting documentation process by converting spoken dialogue into concise, actionable summaries. By leveraging transformer-based models, the project will transcribe the audio content and extract key insights, decisions, and action points, ensuring that important information is easily accessible and reducing the manual effort involved in documenting meetings 🤗.

## Dataset Selection and Objectives
MeetingBank, a benchmark dataset created from the city councils of 6 major U.S. cities to supplement existing datasets. It contains 1,366 meetings with over 3,579 hours of video, as well as transcripts, PDF documents of meeting minutes, agenda, and other metadata. On average, a council meeting is 2.6 hours long and its transcript contains over 28k tokens, making it a valuable testbed for meeting summarizers and for extracting structure from meeting videos. The datasets contains 6,892 segment-level summarization instances for training and evaluating of performance.

For each instance in the dataset, we have:
* MP3 meeting audio
* JSON Transcript containing the words said within their respective timestamps (.e.g "15s-20s: Hello Medtech and goodbye 🤗!"

## **Define Transformer Input Layer**

**TokenEmbedding** converts words into numerical representations while incorporating their positions in a sequence, helping the model understand both meaning and order. 

**SpeechFeatureEmbedding**, on the other hand, extracts meaningful patterns from audio features like spectrograms through convolutional layers, simplifying the data for efficient analysis. Together, they enable systems to handle complex tasks like speech recognition🤗 .

## **Data preprocessing** 

1. Text Preprocessing: The VectorizeChar class converts text transcriptions into integer sequences using a predefined vocabulary and pads the sequences to a fixed length.

2. Audio Preprocessing: The audio files are converted into normalized spectrograms, which are fixed in size by padding or truncating them to a consistent length.

3. Dataset Creation: The preprocessed audio and text data are combined into a TensorFlow dataset that can be efficiently batched and fed into a model for training.

4. TensorFlow Data Pipeline: The use of TensorFlow's Dataset API ensures efficient data handling, including parallel processing and prefetching to speed up training.

This preprocessing pipeline is designed to handle the input data effectively for training a transformer-based ASR system by converting audio and text into suitable formats (spectrograms for audio and integer sequences for text). 🤗🤗