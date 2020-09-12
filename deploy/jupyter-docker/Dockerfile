FROM quay.io/odh-jupyterhub/s2i-spark-minimal-notebook:3.6

USER root

# upgrade pandas and scipy to support TF install
RUN \
    pip3 uninstall -y mlflow && \
    pip3 install uuid pandas==1.0.3 scikit-learn==0.21.3 scipy==1.4.1 kafka-python

USER 1001
