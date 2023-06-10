# Tuwaiq Data Science Bootcamp

## Project 4 : Network data schema in the Netflow

## Team members and their roles :

- Norah Almuhaisen
- Lama Alshabani
- Essa Alhamad

All team members participate in data preprocessing, data cleaning, EDA, create charts, and finally apply the ML model

## Introduction :
Network attacks are unauthorized actions on the digital assets within an organizational network. Malicious parties usually execute network attacks to alter, destroy, or steal private data. Perpetrators in network attacks tend to target network perimeters to gain access to internal systems. 


## Problem Definition
The main problem addressed in this study is to predict Network Attacks depend on PROTOCOL MAP and ip source , ip destination , ... etc with high accuracy 
and This project is focused on developing a machine learning model to detect cyber attacks using network flow data. The network data schema is in the Netflow V9 format

## Dataset Overview :
[Click here](https://www.kaggle.com/datasets/ashtcoder/network-data-schema-in-the-netflow-v9-format?select=train_net.csv)

The database contains 117,174 records and 33 columns containing all the details related to communication and includes 4 classes of cyber attacks:
'None' , 'Port Scanning' , 'Denial of Service' , 'Malware'

 Here is a sample of them:
  
FLOW_ID | PROTOCOL_MAP | L4_SRC_PORT | IPV4_SRC_ADDR | L4_DST_PORT | IPV4_DST_ADDR | FIRST_SWITCHED | FLOW_DURATION_MILLISECONDS | LAST_SWITCHED | PROTOCOL
--------|--------------|-------------|---------------|-------------|----------------|----------------|----------------------------|---------------|----------
370548101 | udp | 50927 | 10.114.226.5 | 53 | 204.61.216.100 | 1647716065 | 1 | 1647716065 | 17
367147345 | icmp | 0 | 34.208.29.22 | 0 | 10.114.224.244 | 1647676228 | 10540 | 1647676239 | 1
369996289 | icmp | 0 | 34.219.129.172 | 0 | 10.114.224.218 | 1647702042 | 0 | 1647702042 | 1
374311525 | tcp | 49738 | 10.114.225.201 | 443 | 185.33.221.15 | 1647780914 | 10472 | 1647780925 | 6



## ML models :
Because we need classify network conncetions, we used classification algorithms and tried KNeighbour, GaussianNB, RandomForest, Support Vector Machine, and Decision Tree. We found the highest accuracy in these three algorithms in order: Decision Tree, GaussianNB, RandomForet.
ML models | accuracy 
--------|--------------
LogisticRegression | 0.87 
LinearDiscriminantAnalysis | 0.98
KNeighborsClassifier | 0.992
DecisionTreeClassifier | 0.9999
GaussianNB | 0.9946
SVC | 0.95 
RandomForestClassifier |0.995 

# Dashboard.
[Click here](https://public.tableau.com/app/profile/norah.almuhaisen/viz/Project4_16864241476640/Dashboard12?publish=yes) to see the dashboard
<img width="800" height="400" alt="Screen Shot 1444-06-17 at 9 20 35 AM" src="images/network.jpg">
