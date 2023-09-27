
+ A module in the context of MSF, is a piece of code that can be utilized by the MSF.

- The MSF libraries facilitate the execution of modules without having to write the code necessary in order to execute them.



![[Pasted image 20230928014629.png]]

### `MSF` Modules

+ **Exploit** - A module that is used to take advantage of vulnerability and is typically paired with a payload.

+ **Payload** - Code that is delivered by `MSF` and remotely executed on the target after successful exploitation. An example of a payload is a reverse shell that initiates a connection from the target system back to the attacker.

+ **Encoder** - Used to encode payloads in order to avoid AV detection. For example, `shikata_ga_nai` is used to encode Windows payloads.

+ **NOPS** - Used to ensure that payloads sizes are consistent and ensure the stability of a payload when executed.

+ **Auxiliary** - A module that is used to perform additional functionality like port scanning and enumeration.

### `MSF` Payload Types

When working with exploits, MSF provides you with two types of payloads that can be paired with an exploit:

1. Non-Staged Payload - Payload that is sent to the target system as is along with the exploit.
2. Staged Payload - A staged payload is sent to the target in two parts, whereby:
	+ The first part (`stager`) contains a payload that is used to establish a reverse connection back to the attacker, download the second part of the payload (stage) and execute it.

### Stagers & Stages

1. Stagers - Stagers are typically used to establish a stable communication channel between the attacker and target, after which a stage payload is downloaded and executed on the target system.

2. Stage - Payload components that are downloaded by the stager.