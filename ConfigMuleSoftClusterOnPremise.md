# Install Mule Runtime Manager On-Premise

Next steps will show the process to follow to install Mulesoft Runtime Manager on Linux Ubuntu distribution for two nodes in the same host. 

> [!NOTE]
> Just as remainder:
>	- Mule runtime versions 4.11.0 and 4.12.2 require Java 17.
>	- Java Compatibility Details
>	 	- Required JDK: Java 17.
>		- Unsupported Versions: Java 8 and Java 11 are not supported for Mule runtime 4.10, 4.11, or 4.12.


1.- Download the installer package [here](https://www.mulesoft.com/lp/dl/anypoint-mule-studio).
>[!NOTE]
> You will get a file named like next:
>
> mule-ee-distribution-standalone-4.12.2.zip

2.- Create base root directory.
```bash
	mkdir /opt/Mulesoft/RuntimeManager
```
	
3.- Create folder according to Runtime Manager version. In this case, the version used was **4.12.2**.
```bash
	cd /opt/Mulesoft/RuntimeManager
	mkdir 4.12.2
```

4.- Go to Runtime Manager version directory created before and create a new directory. For example, **cluster-1**.
```bash
	cd 4.12.2
	mkdir cluster-1
```

5.- Go to cluster-1 directory and create a new directory for node1 and node2. For example, the structure can be like next: 
```bash
	cd /opt/Mulesoft/RuntimeManager/4.12.2/cluster-1
s
	mkdir /opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node1

	mkdir /opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node2
```

6.- In each directory node unzip the Runtime Installer package in order to have the binary for each node.

7.- Go to Runtime Manager Control Plane -> Servers -> click on Add Server button to get the command to register each node into Control Plane. You will get something like this:
```bash
	./amc_setup -H 91180743-e8e1-4514-95a6-fc9dfdf8cd1f---2726449 server-name
```
> [!NOTE]
> You will have to change **server-name** by the name for ech node.

8.- Register node 1. Go to directory **bin** into node1 and execute the command gotten before.
```bash
	cd  /opt/Mulesoft/RuntimeManager/4.12.2/scluster-1/mule-ee-node1/bin

	./amc_setup -H 91180743-e8e1-4514-95a6-fc9dfdf8cd1f---2726449 node1
```
9.- Register node 2.  Go to directory **bin** into node2 and execute the command gotten in step 7.
```bash
	cd  /opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node2/bin

	./amc_setup -H 91180743-e8e1-4514-95a6-fc9dfdf8cd1f---2726449 node2
```
	
10.- Create a server group adding both nodes registered before. Go to Runtime Manager Control Plane -> Servers -> Create Group and provide next values:
- Define Group Name
- Select the Servers

11.- Start node1.
```bash
	/opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node1/bin/mule -M-Dhttp.port=18085
```
	
12.- Start node2.
```bash
	/opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-ee-node2/bin/mule -M-Dhttp.port=28085
```
> [!NOTE]
> Because of that we configured both nodes in the same host we used a different port for each node.

> [!TIP]
> If you have to change the Java version for Runtime Manager follow next steps:
>
> Go to conf/wrapper.config file for each node.
>
> Go to /opt/Mulesoft/RuntimeManager/4.12.2/cluster-1/mule-enterprise-node1/conf
>
> Edith the file: wrapper.config
>
> Set the wished Java version into next property:
>	wrapper.java.command=/opt/jvm/jdk-17.0.9/bin


