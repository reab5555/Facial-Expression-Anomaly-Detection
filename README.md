# Facial-Expression-Anomaly-Detection

This repository contains an advanced algorithm for detecting anomalies in facial expressions and body language over the timeline of a video. The tool extracts faces and postures from video frames, detects unique facial features and body postures, and analyzes them to identify anomalies using time series analysis, specifically utilizing a variational autoencoder (VAE) approach.

## Practical Applications

### Forensic Analysis
- Identify suspicious behavior in surveillance footage.
- Detect stress or duress in interrogation videos.

### Human Intelligence (HUMINT)
- Analyze micro-expressions.
- Monitor and assess emotional states in communications.

## Key Features

- **Face Extraction**: Extracts faces from video frames using the MTCNN model.
- **Feature Embeddings**: Extracts facial feature embeddings using the InceptionResnetV1 model.
- **Body Posture Analysis**: Evaluates body postures using MediaPipe Pose.
- **Anomaly Detection**: Uses Variational Autoencoder (VAE) to detect anomalies in facial expressions and body postures over time.

<img src="appendix/diagram.svg" width="1050" alt="alt text">

## Micro-Expressions
Paul Ekman’s work on facial expressions of emotion identified universal micro-expressions that reveal true emotions. These fleeting expressions, lasting only milliseconds, are challenging to detect but can be captured and analyzed using computer vision algorithms when analyzing frame-by-frame.

## InceptionResnetV1
The InceptionResnetV1 model is a deep convolutional neural network used for facial recognition and facial attribute extraction.

- **Accuracy and Reliability**: Pre-trained on the VGGFace2 dataset, it achieves high accuracy in recognizing and differentiating between faces.
- **Feature Richness**: The embeddings capture rich facial details, essential for recognizing subtle expressions and variations.
- **Global Recognition**: Widely adopted in various facial recognition applications, demonstrating reliability and robustness across different scenarios.

## Variational Autoencoder (VAE)
A Variational Autoencoder (VAE) is a type of neural network that learns to encode input data (like facial embeddings or posture scores) into a latent space and then reconstructs the data from this latent representation. VAEs not only learn to compress data but also to generate new data, making them particularly useful for anomaly detection.

- **Probabilistic Nature**: VAEs introduce a probabilistic approach to encoding, where the encoded representations are not single fixed points but distributions. This allows the model to learn a more robust representation of the data.
- **Reconstruction and Generation**: By comparing the reconstructed data to the original, VAEs can measure reconstruction errors. High errors indicate anomalies, as such data points do not conform well to the learned normal patterns.

### Methods of Anomaly Detection:
1. **Using Full-Dimensional Embeddings**: Directly analyzes the raw facial embeddings without dimensionality reduction.
2. **Using Posture Scores**: Evaluates body posture scores extracted from video frames.

## MediaPipe Pose Model/Library
MediaPipe Pose is a versatile machine learning library designed for high-accuracy real-time posture estimation. Mediapipe Pose uses a deep learning model to detect body landmarks and infer body posture.

- **Real-Time Performance**: Capable of processing video frames at real-time speeds, making it suitable for live video analysis.
- **Accuracy and Precision**: Detects 33 body landmarks, including important joints and key points, enabling detailed posture and movement analysis.
- **Integration**: Easily integrates with other machine learning frameworks and tools, enhancing its versatility for various applications.

## Setup Parameters
- **DESIRED_FPS**: Frames per second to analyze (lower for faster processing).
- **ANOMALY_THRESHOLD**: Threshold for detecting anomalies.

## Output
- **Organized Faces**: Faces organized by detected persons in the `organized_faces` folder.
- **Anomalies Detection Results**: Results and identified anomalies displayed and saved in the project directory.

## Example Scenario

### An Example from a Death Sentence Verdict

<img src="appendix/wade_wilson_2.jpg" width="250" alt="alt text">

Wade Wilson, a 30-year-old from Fort Myers, Florida, was convicted in June 2024 for the October 2019 murders of Kristine Melton and Diane Ruiz in Cape Coral. During the trial, Wilson was notably cold and calm, showing little emotion throughout the proceedings, which many found unsettling. The jury recommended the death penalty, with the final sentencing set for July 23, 2024.

<p align="left">
<img src="appendix/1.jpg" width="50" alt="alt text">
<img src="appendix/2.jpg" width="50" alt="alt text">
<img src="appendix/3.jpg" width="50" alt="alt text">
<img src="appendix/4.jpg" width="50" alt="alt text">
<img src="appendix/5.jpg" width="50" alt="alt text">
<img src="appendix/6.jpg" width="50" alt="alt text">
<p/>

Sources:
1. [Fox News](https://www.foxnews.com/us/florida-double-murderer-viral-smug-soulless-courtroom-demeanor)
2. [WINK News](https://winknews.com/2024/06/13/wade-wilsons-lack-emotion-double-murder-trial/)
3. [YouTube](https://www.youtube.com/watch?v=8j8psgKXmRg)

### Detected Anomalies (Facial Features)
<p align="left">
<img src="appendix/anomaly_scores_all_features_plot.png" width="250" alt="alt text">
<img src="appendix/anomaly_scores_components_plot.png" width="250" alt="alt text">
<img src="appendix/anomaly_scores_embeddings_plot.png" width="250" alt="alt text">
<p/>

### Detected Anomalies (Body Posture)
<p align="left">
<img src="appendix/posture_scores_plot.png" width="250" alt="alt text">
<img src="appendix/posture_mse_plot.png" width="250" alt="alt text">
<p/>

## Conclusion
This tool offers robust solutions for detecting emotional and posture anomalies in video-based facial expressions and body language, beneficial for both forensic analysis and HUMINT operations. By leveraging advanced computer vision techniques and the power of autoencoders, it provides crucial insights into human behavior in a timely manner.
