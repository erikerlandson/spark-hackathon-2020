FROM quay.io/odh-jupyterhub/s2i-spark-minimal-notebook:3.6

USER root

# upgrade pandas and scipy to support TF install
RUN pip3 install uuid pandas==0.23.4 scikit-learn==0.21.3 scipy==1.4.1

USER 1001
