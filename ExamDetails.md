# Exam Details

> This is a collated summary of exam details and tips. Be aware it might become outdated and the official content should be considered.

The online, proctored, performance-based test consists of a set of performance-based items (problems) to be solved in a command line and is expected to take approximately two (2) hours to complete.

This exam curriculum includes these general domains and their weights on the exam:

    13% – Core Concepts
    18% – Configuration
    10% – Multi-Container Pods
    18% – Observability
    20% – Pod Design
    13% – Services & Networking
    8% – State Persistence

You can take the CKA exam and the CKAD exam from any qualifying computer, anywhere there is internet, almost any time. No need to go to a test center. 

The online exams consist of a set of performance-based tasks (problems) to be solved on the command line. **CKAD exam consists of 19 tasks**. CKA exam consists of 24 tasks. 

The CKAD exam is expected to take 2 hours to complete.
The CKA exam is expected to take 3 hours to complete. 

Candidates are required to provide a non-expired Primary ID that contains Candidate’s photograph, signature and full name (see examples of acceptable forms of ID in the table below).

If the Candidate’s full name on their Primary ID contains non-latin characters, then the Candidatemust ALSO provide a non-expired Secondary ID containing their full name in Latin Charactersand signature, OR a notarized English translation of their Primary ID along with the non-latincharacter Primary ID

---
## Exam Results

Results will be emailed 36 hours from the time that the exam was completed.

Results will also be made available on My Portal

---
## Exam Environment

Each task on this exam must be completed on a designated cluster/configuration context.

To minimize switching, the tasks are grouped so that all questions on a given cluster appearconsecutively.

There are four clusters for (CKAD) that comprise the exam environment, madeup of varying numbers of containers, as follows:

**CKAD Clusters**

Cluster | Members | CNI | Description 
------- | ------- | --- | -----------
k8s  | 1 master, 2 workers | flannel | k8s cluster
dk8s | 1 master, 1 workers | flannel | k8s cluster
nk8s | 1 master, 2 workers | calico  | k8s cluster
sk8s | 1 master, 1 workers | flannel | k8s cluster


The CKA & CKAD environments are currently running **Kubernetes v​1.18**. (Quarterly exam updates are planned to match Kubernetes releases.)

At the start of each task you'll be provided with the command to ensure you are on the correctcluster to complete the task

Nodes making up each cluster can be reached via​ ssh​, using a command such as the following: `ssh <nodename>`

You can assume elevated privileges on any node by issuing the following command: `​sudo -i`

You can also use `​sudo`​ to execute commands with elevated privileges at any time

You must return to the base node (hostname ​`node-1​`) after completing each task.

Nested​ `−ssh` is not supported

You can use `​kubectl` ​and the appropriate context to work on any cluster from the base node.When connected to a cluster member via ​`ssh`​, you will only be able to work on that particularcluster via ​kubectl.

Further instructions for connecting to cluster nodes will be provided in the appropriate tasks

Where no explicit namespace is specified, the default namespace should be acted upon.

If you need to destroy/recreate a resource to perform a certain task, it is your responsibility toback up the resource definition appropriately prior to destroying the resource.

---
## Technical Instructions

You may access these instructions at any time while taking the exam by typing `man lf_exam`.

 1. Root privileges can be obtained by running `sudo −i`.

 2. Rebooting of your server IS permitted at anytime.

 3. Do not stop or tamper with the certerminal process as this will **END YOUR EXAM SESSION**.

 4. Do not block incoming ports 8080/tcp, 4505/tcp and 4506/tcp. This includes firewall rules that arefound within the distribution's default firewall configuration files as well as interactive firewallcommands.

 5. Use Ctrl+Alt+W instead of Ctrl+W.

     5.1. `Ctrl+W` is a keyboard shortcut that will close the current tab in Google Chrome.

 6. `Ctrl+C` & and `Ctrl+V` are not supported in your exam terminal.To copy and paste text, please use;
 
     6.1. For Linux: select text for copy and middle button for paste (or both left and rightsimultaneously if you have no middle button).

     6.2. For Mac: `⌘+C` to copy and `⌘+V` to paste.

     6.3. For Windows: `Ctrl+Insert` to copy and `Shift+Insert` to paste.

     6.4. In addition, you might find it helpful to use the Notepad (see top menu under 'ExamControls') to manipulate text before pasting to the command line.

 7. Installation of services and applications included in this exam may require modification of systemsecurity policies to successfully complete.
 8. Only a single terminal console is available during the exam. Terminal multiplexers such as GNUScreen and tmux can be used to create virtual console