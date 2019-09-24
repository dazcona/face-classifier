# Face Classifier

Code adapted from the following publication:

Real-time face detection and emotion / gender classification using fer2013 / IMDB datasets with a keras CNN model and openCV - https://github.com/oarriaga/face_classification

API developed on top of the code: https://github.com/enric1994/face-classifier

We run the API for each image frame to detect emotion and gender classifications and save them.

## Usage

1. Download the code:
```
$ git clone https://github.com/dazcona/face-classifier.git
```

2. Mount the dataset as drive in */datasets* in *docker-compose.yml*. As an example:
```
volumes:
  - /Volumes/HDD/datasets/:/datasets
```

3. Build our docker image:
```
$ cd docker
$ make build
```

4. Create a docker container based on the image:
```
$ make run
```

5. SSH to the docker container:
```
$ make dev
```

6. Extract emotion features from both groundtruth and test frames:
```
$ python src/extract_emotions.py
```

## Output

In a picture, for each face, the score of the 7 emotions (anger, disgust, fear, happiness, sadness, surprise, neutral), gender scores and spatial information is given:
```
{
  "results": [
    {
      "emotion_prediction0": "0.00129826", 
      "emotion_prediction1": "0.00065926", 
      "emotion_prediction2": "0.00391912", 
      "emotion_prediction3": "0.927588", 
      "emotion_prediction4": "0.00134277", 
      "emotion_prediction5": "0.00428354", 
      "emotion_prediction6": "0.0609093", 
      "gender_prediction_female": "0.123496", 
      "gender_prediction_male": "0.876504", 
      "x1": "308", 
      "x2": "419", 
      "y1": "349", 
      "y2": "460"
    }, 
    {
      "emotion_prediction0": "0.00875436", 
      "emotion_prediction1": "0.000152118", 
      "emotion_prediction2": "0.0148069", 
      "emotion_prediction3": "0.647762", 
      "emotion_prediction4": "0.0199056", 
      "emotion_prediction5": "0.00784853", 
      "emotion_prediction6": "0.300771", 
      "gender_prediction_female": "0.156928", 
      "gender_prediction_male": "0.843072", 
      "x1": "845", 
      "x2": "952", 
      "y1": "373", 
      "y2": "480"
    }, 
    {
      "emotion_prediction0": "0.00286031", 
      "emotion_prediction1": "0.000891097", 
      "emotion_prediction2": "0.0024018", 
      "emotion_prediction3": "0.973004", 
      "emotion_prediction4": "0.00267297", 
      "emotion_prediction5": "0.000232481", 
      "emotion_prediction6": "0.0179375", 
      "gender_prediction_female": "0.371204", 
      "gender_prediction_male": "0.628796", 
      "x1": "1535", 
      "x2": "1624", 
      "y1": "384", 
      "y2": "473"
    }, 
    {
      "emotion_prediction0": "0.00313305", 
      "emotion_prediction1": "0.000271041", 
      "emotion_prediction2": "0.00641955", 
      "emotion_prediction3": "0.953762", 
      "emotion_prediction4": "0.000719945", 
      "emotion_prediction5": "0.000361913", 
      "emotion_prediction6": "0.035333", 
      "gender_prediction_female": "0.0449619", 
      "gender_prediction_male": "0.955038", 
      "x1": "1187", 
      "x2": "1293", 
      "y1": "400", 
      "y2": "506"
    }, 
    {
      "emotion_prediction0": "0.00517767", 
      "emotion_prediction1": "0.000317627", 
      "emotion_prediction2": "0.0247479", 
      "emotion_prediction3": "0.791406", 
      "emotion_prediction4": "0.0631129", 
      "emotion_prediction5": "0.0090672", 
      "emotion_prediction6": "0.106171", 
      "gender_prediction_female": "0.747512", 
      "gender_prediction_male": "0.252488", 
      "x1": "576", 
      "x2": "681", 
      "y1": "422", 
      "y2": "527"
    }, 
    {
      "emotion_prediction0": "0.044323", 
      "emotion_prediction1": "1.00535e-05", 
      "emotion_prediction2": "0.411591", 
      "emotion_prediction3": "0.0032644", 
      "emotion_prediction4": "0.100822", 
      "emotion_prediction5": "0.0830095", 
      "emotion_prediction6": "0.35698", 
      "gender_prediction_female": "0.318393", 
      "gender_prediction_male": "0.681607", 
      "x1": "784", 
      "x2": "1343", 
      "y1": "860", 
      "y2": "1419"
    }, 
    {
      "emotion_prediction0": "0.137723", 
      "emotion_prediction1": "0.00092637", 
      "emotion_prediction2": "0.0799326", 
      "emotion_prediction3": "0.196257", 
      "emotion_prediction4": "0.419781", 
      "emotion_prediction5": "0.0413914", 
      "emotion_prediction6": "0.123989", 
      "gender_prediction_female": "0.261925", 
      "gender_prediction_male": "0.738075", 
      "x1": "1609", 
      "x2": "1662", 
      "y1": "1213", 
      "y2": "1266"
    }
  ]
}
```
