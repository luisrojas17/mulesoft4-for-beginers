# Process to Install Mule Runtime Manager

Next steps will show the steps to install Mulesoft Runtime Manager. 

> [!NOTE]
> Just as remainder:
>	- Mule runtime versions 4.11.0 and 4.12.2 require Java 17.
>	- Java Compatibility Details
>	 	- Required JDK: Java 17.
>		- Unsupported Versions: Java 8 and Java 11 are not supported for Mule runtime 4.10, 4.11, or 4.12.
	
Install the Runtime Manager into:
	/opt/Mulesoft/RuntimeManager/
	
Create folder with runtime manager version. For example:
	mkdir 4.12.2

./amc_setup -H 91180743-e8e1-4514-95a6-fc9dfdf8cd1f---2726449 node1

Go to bin directory for node1
	cd  /opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node1/bin

Execute the agent setup file 
	./amc_setup -H 91180743-e8e1-4514-95a6-fc9dfdf8cd1f---2726449 node1

Go to bin directory for node2
	cd  /opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node2/bin

Execute the agent setup file
	./amc_setup -H 91180743-e8e1-4514-95a6-fc9dfdf8cd1f---2726449 node2
	
Start runtime manager node1
	/opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node1/bin/mule -M-Dhttp.port=18085
	
Start runtime manager node2
	/opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node2/bin/mule -M-Dhttp.port=28085
	
Go to Runtime Manager
	- Create a group adding both nodes

Change the Java version for Runtie Manager

Go to conf/wrapper.config file for each node. For instance
Go to /opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-enterprise-node27/conf
Edith the file: wrapper.config
Set the wished Java version into next property:
	wrapper.java.command=/opt/jvm/jdk-17.0.9/bin


