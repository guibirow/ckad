# Exam Details

> This is a collated summary of exam details and tips. Be aware it might become outdated and the official content should be considered.

The online, proctored, performance-based test consists of a set of performance-based items (problems) to be solved in a command line and is expected to take approximately two (2) hours to complete.

This exam curriculum includes these general domains and their weights on the exam:

- 13% – Core Concepts  
- 18% – Configuration  
- 10% – Multi-Container Pods  
- 18% – Observability  
- 20% – Pod Design  
- 13% – Services & Networking  
- 8% – State Persistence  

You can take the CKA exam and the CKAD exam from any qualifying computer, anywhere there is internet, almost any time. No need to go to a test center. 

The online exams consist of a set of performance-based tasks (problems) to be solved on the command line. **CKAD exam consists of 19 tasks**. CKA exam consists of 24 tasks. 

The CKAD exam is expected to take 2 hours to complete.
The CKA exam is expected to take 3 hours to complete. 

Candidates are required to provide a non-expired Primary ID that contains Candidate’s photograph, signature and full name (see examples of acceptable forms of ID in the table below).

If the Candidate’s full name on their Primary ID contains non-latin characters, then the Candidatemust ALSO provide a non-expired Secondary ID containing their full name in Latin Charactersand signature, OR a notarized English translation of their Primary ID along with the non-latincharacter Primary ID

---
## CKAD Exam Curriculum

> The curriculum below reflects the current version 1.18, previous versions can be foung on [cncf curriculum](https://github.com/cncf/curriculum)  

13% – Core Concepts  
- Understand Kubernetes API primitives
- Create and configure basic Pods

18% – Configuration  
- Understand ConfigMaps
- Understand SecurityContexts
- Define an application’s resource
requirements
- Create & consume Secrets
- Understand ServiceAccounts

10% – Multi-Container Pods  
- Understand Multi-Container Pod design
patterns (e .g. ambassador, adapter,
sidecar)

18% – Observability  
- Understand LivenessProbes and
ReadinessProbes
- Understand container logging
- Understand how to monitor applications
in Kubernetes
- Understand debugging in Kubernetes

20% – Pod Design  
- Understand Deployments and how to perform
rolling updates
- Understand Deployments and how to perform
rollbacks
- Understand Jobs and CronJobs
- Understand how to use Labels, Selectors,
and Annotations

13% – Services & Networking  
- Understand Services
- Demonstrate basic understanding of NetworkPolicies 

8% – State Persistence  
- Understand PersistentVolumeClaims for storage


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


# FAQ

#### How is the exam proctored?

The certification exam is proctored remotely during the exam session via streaming audio, video, and screen sharing feeds. The screen sharing feed allows proctors to view candidates desktops (including all monitors). The audio, video, and screen sharing feeds will be stored for alimited period of time in the event that there is a subsequent need for review.

---
#### How long will the exam take?
Candidate’s have a maximum of 2 hours (CKAD) to complete the exam.

---
#### How long is my certification valid for?

CKA and CKAD Certifications are valid for 3 years.Candidates may keep the certification valid by completing the renewal requirement optionbelow. Renewal requirements must be completed prior to the expiration of the certification.

---
#### What version of Kubernetes is running in the Exam Environment?
The exam environment is currently running Kubernetes v1.18

---
#### What resources am I allowed to access during my exam?

Candidates may use their Chrome or Chromium browser to open one additional tab in order toaccess assets at: ​https://kubernetes.io/docs/​, ​https://github.com/kubernetes/​,ttps://kubernetes.io/blog/​ and their subdomains. This includes all available language translationsof these pages (e.g. ​https://kubernetes.io/zh/docs/)

No other tabs may be opened and no other sites may be navigated to.The allowed sites above may contain links that point to external sites. It is the responsibility ofthe candidate not to click on any links that cause them to navigate to a domain that is notallowed.

---
#### May I take notes during the exam?

Yes, you can take notes using the Notepad feature accessible in the top menu bar of the examconsole, or use a text file in the command line terminal. Please be aware that notes enteredhere will not be retained or accessible after the exam has ended. Ask your proctor if you needhelp operating the Notepad.

--- 
#### What score is needed to pass the exam?

For the CKAD Exam, a score of 66% or above must be earned to pass. For the CKA Exam, a score of 74% or above must be earned to pass.

---
#### How is my exam scored?

Exams are scored automatically, usually within 24 hours of completion. Results will be emailed within 36  hours from the time that the Exam was ​completed​.  Results will also be madeavailable on [​My Portal​](https://training.cncf.io/portal).

Exams are graded for results. There may be more than one way to perform an objective on anExam and unless otherwise specified, the candidate can pick any available path to perform theobjective as long as it produces the correct result

---
#### Am I able to retake the exam?

For exams purchased directly from The **Cloud Native Computing Foundation**, one (1) free retakeper exam purchase will be granted in the event that a passing score is not achieved and candidate has not otherwise been deemed ineligible for certification or retake. Unless otherwise indicated in the exam order, the free retake must be completed within 12 months of the date ofthe original exam purchase.  After the free retake has been exhausted or the deadline to complete the free retake has passed, candidates may register and pay to take the exam again,with no discount given for such additional retakes.

For purchases made through an Authorized Training Partner (ATP), please contact the ATPregarding eligibility for a free retake

---
#### What are the system requirements to take the exam?

Exams are delivered online and closely monitored by proctors via webcam, audio, and remotescreen viewing.  
Candidates must provide their own front-end hardware to take exams,including a computer with:
- Chrome or Chromium browser
- reliable internet access
- webcam
- microphone

The workstation on which the hardware (i.e. desktop or laptop) is placed must, aside from therequired hardware, reveal a clean surface with no obstructions overhead or underneath.Candidates should ensure that their webcam is capable of being moved in case the proctorrequests that the Candidate pan their surroundings to check for potential violations of exampolicy.

Candidates should run the [​compatibility check tool​](https://www.examslocal.com/ScheduleExam/Home/CompatibilityCheck) provided by the Exam Proctoring Partner toverify that their hardware meets the minimum requirements.  Select “Linux Foundation” as theExam Sponsor and “CKA” or “CKAD” as the Exam.  (At this time, only Chrome and Chromiumbrowsers are supported.)

---
#### What are the ID requirements to take the exam?

Candidates are required to provide a non-expired Primary ID that contains Candidate’s photograph, signature and full name.

**Primary ID(non-expired and including photographand signature)**

- Passport
- Government-issued driver’s license/permit
- Government-Issued local language ID (withphoto and signature)
- National Identity card
- State or province-issued identity card

If the Candidate’s full name on their Primary ID contains non-latin characters, then theCandidate must ALSO provide a non-expired Secondary ID containing their full name in LatinCharacters and signature, OR a notarized English translation of their Primary ID along with thenon-latin character Primary ID.

**SecondaryID(non-expired and including signature withCandidate name in Latin characters)**

- Debit (ATM) Card
- Credit CardHealth Insurance - Card
- U.S. Social Security Card 

If you have questions about whether your photo ID is acceptable please contact cncf for more information.

> Exams **may be administered** to citizens of a US sanctioned country **PROVIDED the citizens are tested OUTSIDE** the sanctioned country and their exam registration and current ID show an address OUTSIDE the sanctioned country. Please check the list of allowed contries on Linux foundation website.