FROM quay.io/opendatahub/spark-cluster-image:spark22python36

USER root

RUN \
    /opt/rh/rh-python36/root/usr/bin/pip3 uninstall -y mlflow && \
    /opt/rh/rh-python36/root/usr/bin/pip3 install uuid pandas==1.0.3 scikit-learn==0.21.3 scipy==1.4.1

USER 1001
