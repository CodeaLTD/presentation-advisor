FROM tensorflow/serving:latest

ENV MODEL_NAME=recommender_system

COPY exported_model /models/recommender_system

EXPOSE 8500
EXPOSE 8501

ENTRYPOINT ["/usr/bin/tensorflow_model_server", "--rest_api_port=8501", "--model_name=recommender_system", "--model_base_path=/models/recommender_system"]
