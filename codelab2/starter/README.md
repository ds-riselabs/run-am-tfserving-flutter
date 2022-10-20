# Flutter Project to demonstrate sending requests to TF Serving

This Flutter project demostrate how to call TF Serving from a Flutter app, via
gRPC and REST. You can input some text and it will send the text (news headline) to TF Serving
to verify the news headline as either coming from verified source or not.

### `Note` -  If you don't already have docker downloaded on your opertating system, download docker to your operating system!


## Usage

1. Download the news-source-verification SavedModel from this [codelab](https://colab.research.google.com/drive/1B7Chznw07H83dp6f8fOZCIvkMJ7K-KwY?usp=sharing).

#### Start TensorFlow Serving
In your terminal, start TensorFlow Serving with Docker, but replace the `PATH/TO/SAVEDMODEL` placeholder with the absolute path of the `mm_runam_savedmodel` folder on your computer.

2. Start TF Serving with: 
- `docker pull tensorflow/serving`
- `docker run -t --rm -p 8500:8500 -p 8501:8501 -v
   "PATH/TO/SAVEDMODEL:/models/news-source-verification" -e MODEL_NAME=news-source-verification
   tensorflow/serving`.  

3. Go into `lib/proto` folder and run `generate_grpc_stub_dart.sh` to generate the gRPC
   client stub.
4. Start Android emulator and run the app.
5. If you are not using an Android emulator, make sure to replace '10.0.2.2'
   with your TF Serving host's IP address.

