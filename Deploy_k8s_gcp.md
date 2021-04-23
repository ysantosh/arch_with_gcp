Introduction to Docker
In this lab you will familiarize yourself with the basic Docker container environment commands. You will create, run, and debug containers, and learn to pull and push images to and from Google Container Registry.
Kubernetes Engine: Qwik Start
Google Kubernetes Engine provides a managed environment for deploying, managing, and scaling your containerized applications using Google infrastructure. This hands-on lab shows you how deploy a containerized application with Kubernetes Engine. Watch the short video Manage Containerized Apps with Kubernetes Engine.
Orchestrating the Cloud with Kubernetes
In this lab you will learn how to provision a complete Kubernetes cluster using Google Container Engine; deploy and manage Docker containers using kubectl; and break an application into microservices using Kubernetes’ Deployments and Services.
```
Welcome to Cloud Shell! Type "help" to get started.
Your Cloud Platform project in this session is set to qwiklabs-gcp-03-eb0de0cb52ee.
Use “gcloud config set project [PROJECT_ID]” to change to a different project.
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
README-cloudshell.txt
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ gsutil cp -r gs://spls/gsp021/* .
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/HEAD...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/config...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/description...
- [3 files][  361.0 B/  361.0 B]
==> NOTE: You are performing a sequence of gsutil operations that may
run significantly faster if you instead use gsutil -m cp ... Please
see the -m section under "gsutil help options" for further information
about when gsutil -m can be advantageous.

Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/applypatch-msg.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/commit-msg.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/fsmonitor-watchman.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/post-update.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/pre-applypatch.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/pre-commit.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/pre-push.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/pre-rebase.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/pre-receive.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/prepare-commit-msg.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/hooks/update.sample...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/index...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/info/exclude...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/logs/HEAD...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/logs/refs/heads/master...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/logs/refs/remotes/origin/HEAD...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/00/3cec4f1b60af35c100072af6fb3c08661b7c1a...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/02/1045ed5654fe659c68ff1e227d097e96218ad9...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/03/69e9021e870d8e0a3f901ad12430c313e64170...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/03/6a7cccf5377d5da982d3570b686dd46dc46ecd...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/06/f7eccdd621cad86710d2f11d36823e68324600...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/09/2b7773dbc7c3a41355270b196cd8fc0c19e7f2...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/09/80232e617219a67ad57da7472fc643aff6def6...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/0b/83cec4e65254cb6315c772f97e1fd94d3ab214...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/0c/287d4607de60e405d354d7201b25d2a3f492c8...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/12/516ddb42a309650e7aee43adc9e8f491470918...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/16/6fcd6095cbf19c57198bc9fc9ce0fbaffb43f9...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/19/228bd6bf90d004de67c09a2bb86fbd92d9e9cc...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/1f/e779bcf156c392627afccc44922d506c06f315...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/20/4bb4e9651f407dfd81a58f715e95d49b84cfba...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/21/89a47794fd5b592aaeac939a66a85917483a31...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/22/36a0da90acdf6182fcbb6ac076bd2da32ff000...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/24/998705e44deed51c09a7c55e218ff074b6c34a...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/25/535ff347ee434f2da7851e7501af50bdba0a2f...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/26/8167d020044ae3f91c90aa1da611b81bc311aa...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/27/2d355afb62ef37c1f4c7508e8216bc804666d5...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/2d/69c3d3d3aeceb9ca4c47ff28d64d8aad176889...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/2e/34b7d353738c0cce66343dd5cc0670746fc3e8...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/32/da1368260cd9f24e6ea41364d8e2a934d51361...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/34/04c8d5d0789596d5eaf3a7f97f45028e27f2e0...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/37/23ed58d9f123bed49053d66a8123b005416c6d...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/46/499de05a9e3ce017e7e2ca96e2f255a38e0108...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/47/9308e5f5254f64cdd1f1b7609e8d5768b80aec...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/48/19aa58ec6e80bdbb91923cfdfe1ecba32a6137...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/4e/4bc74c6e3ecaa71ef688b72ef4a003453e106e...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/59/6b70ca0fd7318ed0f374d8c33cb50222328dda...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/5c/63d3230677e7fe2b09f9c0ac7ef6265fd209e1...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/5c/d15de4dfe4cf2836afc2f3902d566518119cc6...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/5c/df68701c0c6b97f537c592e3f2df9b808f9db3...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/5d/11d54064a7d153ad33babc565afc3714664f30...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/61/03835f632ef57b9eb08d65c5d3d6207d02b425...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/61/f21ac1117df93cbc2650ce9e2345aab815d13c...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/63/0bb766ee2c1812147f785ffdca3c94bf56f5ac...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/63/6133b0f8382be8742b3b18dcc78c43d49e1132...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/67/c4bebfb5f340d55dcebdec6c7c7743462695d2...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/67/ffa615c795003ba4b3a1d693ce4c7ce9f31a27...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/6b/5ff4a34dbdb1dc1f678475483209b2545a81f6...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/6e/9c67d5633eff9ca749bca2257e1e1fe2548698...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/6f/5f3d1bf673c822bdccf253c2bf7588c0ff2ed8...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/71/deb4e418f3f3223790548670bdfd37534bf666...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/7b/d2bd68f4d3d75aa9e185fa9f97f151fda85340...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/7f/8a88f59f9adb6db90db2245fe96a6b7e4d4b7c...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/85/895faefec94252ce297ea50feb2e9505e5fe69...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/85/ee013323592fbeafb837ceb9270172647f2b8c...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/86/64c23a158798578e5d42440016a68ac3b04a07...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/86/f4a67742560f14fdcececce20a058b75148402...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/89/b3769bbb3b5fb565178ccd66d03e69e41038ee...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/8c/47471efb13225d4249da0e7379b993c9689d54...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/8c/6e788b4148e07f27083afbed6a12126379644e...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/8d/ada3edaf50dbc082c9a125058f25def75e625a...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/8e/fcd3235d9185a67cec49232cccb14cdc8384e2...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/8f/770d40965afdb77c27d86e4fbfd2d70853932f...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/92/a517b2445fc96c43b8cf86097648d187149d7d...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/99/4e01454cc6cd676b18afca07337b7bf9b7b7c2...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/9e/b85a2e9ebcef0fb388b8f7c50602d9b3ef3419...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/a2/a903fd8de5d98b83765bcceeb1c50ca358f1ac...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/a6/b224cde2907c2bab5764b654c543c848d44c27...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/af/4e6d1c65ea37cd37a641b08cfcd3022f69f0c9...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/af/96521650dd9834e3341b5e6cebc821d85a1716...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/b0/b70547b933cedf26075050c2e35df22284cbb0...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/b0/cb83da75e86c1b39c710f68be55ffa569e0413...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/b0/f0dd5287d00b32b10c2bb99e3eaee147705af9...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/b7/6d51b4ac67b6fcb44b498487da6c83751699bb...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/be/0c8183fe7e154564b349b09cafb34c2a06f75c...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/be/6df2a25a8edf6a30dfe763ea3aec7339f465ce...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/c3/19306fa1a460c032eae80c12f3be1ad86c4af3...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/c3/3e8151f1b9c3737499778e80348cb3fa2f6d30...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/c5/13f4a612a10f66ba5c3c98b3eb1275288f398b...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/cc/080e5c11d167b0f16b5bb30ced56c062e5c5b7...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/cc/51815c55c945a27c34bfb87c180adaa1565bcd...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/ce/9c4053ec356ec27e99542c46438b3f65215f4e...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/ce/aa6726c2c86dcd7fa9d0b579c2a68ceb59976a...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/d1/7e743fecc5d6625a31f76811fafdfbd698e3f0...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/da/746e8bbc11364dc5b0eb4a51c3b147eb0a531f...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/db/bebb09e66e26b1e16a1aa65c34f2f495896c56...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/e3/315a105758fb7407a5a834f0dfb06b4f95ebe4...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/e7/81ac28725ce17c35f39bc0b6b49f1a7f3c57e8...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/e9/f25feb4bf41f6e54a5b9137bd34952f8f2f145...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/eb/2246c215774a74d18bb2b31a70591d8c6c86b3...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/ed/0a2e71cfb2fce07f8afb6420b88a639c87630a...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/ef/4190ef2189a7e354afefeb7598cabbe39e50a3...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/f1/f2a4c615439d9d3135787ba4972f70fd68d9fd...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/f2/3eb16fdf193af369aa637db31324d8ae648eb6...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/f6/7797c823fe5726d65f96b83f03783d1001a5b4...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/f8/751d062d4c0fa4361d53c7c2301cfa081c0c56...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/objects/fd/c29c8470849e75061af1264622dbf12a2e3f1f...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/packed-refs...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/refs/heads/master...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/.git/refs/remotes/origin/HEAD...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/CONTRIBUTING.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/LICENSE...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/README.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/cleanup.sh...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/cleanup.sh...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/deployments/auth.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/deployments/frontend.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/deployments/hello-canary.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/deployments/hello-green.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/deployments/hello.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/nginx/frontend.conf...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/nginx/proxy.conf...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/pods/healthy-monolith.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/pods/monolith.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/pods/secure-monolith.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/services/auth.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/services/frontend.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/services/hello-blue.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/services/hello-green.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/services/hello.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/services/monolith.yaml...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/tls/ca-key.pem...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/tls/ca.pem...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/tls/cert.pem...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/kubernetes/tls/key.pem...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/configure-networking.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/create-gce-account.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/creating-and-managing-deployments.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/creating-and-managing-pods.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/creating-and-managing-services.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/download-a-kubernetes-release.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/enable-and-explore-cloud-shell.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/install-and-configure-apiserver.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/install-and-configure-controller-manager.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/install-and-configure-docker.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/install-and-configure-etcd.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/install-and-configure-kubectl.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/install-and-configure-kubelet.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/install-and-configure-scheduler.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/managing-application-configurations-and-secrets.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/monitoring-and-health-checks.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/provision-kubernetes-cluster-with-gke.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/provisioning-ubuntu-on-gce.md...
Copying gs://spls/gsp021/orchestrate-with-kubernetes/labs/rolling-out-updates.md...
\ [156 files][201.4 KiB/201.4 KiB]    5.3 KiB/s
==> NOTE: You are performing a sequence of gsutil operations that may
run significantly faster if you instead use gsutil -m cp ... Please
see the -m section under "gsutil help options" for further information
about when gsutil -m can be advantageous.


Operation completed over 156 objects/201.4 KiB.
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
orchestrate-with-kubernetes  README-cloudshell.txt
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
orchestrate-with-kubernetes  README-cloudshell.txt
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ cd orchestrate-with-kubernetes/
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
cleanup.sh  CONTRIBUTING.md  kubernetes  labs  LICENSE  README.md
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ cat cleanup.sh
# Copyright 2016 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

gcloud compute instances delete node0 node1
gcloud compute routes delete default-route-10-200-1-0-24 default-route-10-200-0-0-24
gcloud compute firewall-rules delete default-allow-local-api
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ cd ..
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
orchestrate-with-kubernetes  README-cloudshell.txt
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ cd
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ gcloud auth list
           Credentialed Accounts
ACTIVE  ACCOUNT
*       student-03-e637940a35a5@qwiklabs.net

To set the active account, run:
    $ gcloud config set account `ACCOUNT`

student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ gcloud container clusters list
NAME  LOCATION       MASTER_VERSION   MASTER_IP       MACHINE_TYPE  NODE_VERSION     NUM_NODES  STATUS
io    us-central1-b  1.18.16-gke.502  35.188.172.116  e2-medium     1.18.16-gke.502  3          RUNNING
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
orchestrate-with-kubernetes  README-cloudshell.txt
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ cd orchestrate-with-kubernetes/
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
cleanup.sh  CONTRIBUTING.md  kubernetes  labs  LICENSE  README.md
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ cd kubernetes/
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
cleanup.sh  deployments  nginx  pods  services  tls
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
cleanup.sh  deployments  nginx  pods  services  tls
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
cleanup.sh  deployments  nginx  pods  services  tls
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ ls -l
total 24
-rw-r--r-- 1 student_03_e637940a35a5 student_03_e637940a35a5  283 Apr 23 04:45 cleanup.sh
drwxr-xr-x 2 student_03_e637940a35a5 student_03_e637940a35a5 4096 Apr 23 04:45 deployments
drwxr-xr-x 2 student_03_e637940a35a5 student_03_e637940a35a5 4096 Apr 23 04:45 nginx
drwxr-xr-x 2 student_03_e637940a35a5 student_03_e637940a35a5 4096 Apr 23 04:45 pods
drwxr-xr-x 2 student_03_e637940a35a5 student_03_e637940a35a5 4096 Apr 23 04:45 services
drwxr-xr-x 2 student_03_e637940a35a5 student_03_e637940a35a5 4096 Apr 23 04:45 tls
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create deployment nginx --image=nginx:1.10.0
deployment.apps/nginx created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get pods
NAME                     READY   STATUS    RESTARTS   AGE
nginx-55c6b6cb9c-r47wk   1/1     Running   0          12s
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl expose deployment nginx --port 80 --type LoadBalancer
service/nginx exposed
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get services
NAME         TYPE           CLUSTER-IP    EXTERNAL-IP   PORT(S)        AGE
kubernetes   ClusterIP      10.3.240.1    <none>        443/TCP        5m34s
nginx        LoadBalancer   10.3.245.45   <pending>     80:30069/TCP   7s
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get services
NAME         TYPE           CLUSTER-IP    EXTERNAL-IP   PORT(S)        AGE
kubernetes   ClusterIP      10.3.240.1    <none>        443/TCP        5m59s
nginx        LoadBalancer   10.3.245.45   <pending>     80:30069/TCP   32s
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get services
NAME         TYPE           CLUSTER-IP    EXTERNAL-IP      PORT(S)        AGE
kubernetes   ClusterIP      10.3.240.1    <none>           443/TCP        6m12s
nginx        LoadBalancer   10.3.245.45   35.238.202.245   80:30069/TCP   45s
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get services
NAME         TYPE           CLUSTER-IP    EXTERNAL-IP      PORT(S)        AGE
kubernetes   ClusterIP      10.3.240.1    <none>           443/TCP        6m20s
nginx        LoadBalancer   10.3.245.45   35.238.202.245   80:30069/TCP   53s
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ cat pods/monolith.yaml
apiVersion: v1
kind: Pod
metadata:
  name: monolith
  labels:
    app: monolith
spec:
  containers:
    - name: monolith
      image: kelseyhightower/monolith:1.0.0
      args:
        - "-http=0.0.0.0:80"
        - "-health=0.0.0.0:81"
        - "-secret=secret"
      ports:
        - name: http
          containerPort: 80
        - name: health
          containerPort: 81
      resources:
        limits:
          cpu: 0.2
          memory: "10Mi"
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f pods/monolith.yaml
pod/monolith created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get pods
NAME                     READY   STATUS    RESTARTS   AGE
monolith                 1/1     Running   0          5s
nginx-55c6b6cb9c-r47wk   1/1     Running   0          2m7s
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl describe pods monolith
Name:         monolith
Namespace:    default
Priority:     0
Node:         gke-io-default-pool-ff1906d4-pdk8/10.128.0.3
Start Time:   Fri, 23 Apr 2021 04:51:46 +0000
Labels:       app=monolith
Annotations:  <none>
Status:       Running
IP:           10.0.2.4
IPs:
  IP:  10.0.2.4
Containers:
  monolith:
    Container ID:  docker://0a8f65a0945e12f995251636fdc042d6c6a533c8e023fe7d24551c10d479c31e
    Image:         kelseyhightower/monolith:1.0.0
    Image ID:      docker-pullable://kelseyhightower/monolith@sha256:72c3f41b6b01c21d9fdd2f45a89c6e5d59b8299b52d7dd0c9491745e73db3a35
    Ports:         80/TCP, 81/TCP
    Host Ports:    0/TCP, 0/TCP
    Args:
      -http=0.0.0.0:80
      -health=0.0.0.0:81
      -secret=secret
    State:          Running
      Started:      Fri, 23 Apr 2021 04:51:48 +0000
    Ready:          True
    Restart Count:  0
    Limits:
      cpu:     200m
      memory:  10Mi
    Requests:
      cpu:        200m
      memory:     10Mi
    Environment:  <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from default-token-d4sqg (ro)
Conditions:
  Type              Status
  Initialized       True
  Ready             True
  ContainersReady   True
  PodScheduled      True
Volumes:
  default-token-d4sqg:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  default-token-d4sqg
    Optional:    false
QoS Class:       Guaranteed
Node-Selectors:  <none>
Tolerations:     node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                 node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  10s   default-scheduler  Successfully assigned default/monolith to gke-io-default-pool-ff1906d4-pdk8
  Normal  Pulling    9s    kubelet            Pulling image "kelseyhightower/monolith:1.0.0"
  Normal  Pulled     8s    kubelet            Successfully pulled image "kelseyhightower/monolith:1.0.0"
  Normal  Created    8s    kubelet            Created container monolith
  Normal  Started    8s    kubelet            Started container monolith
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl port-forward monolith 10080:80
Forwarding from 127.0.0.1:10080 -> 80
curl http://127.0.0.1:10080Handling connection for 10080
Handling connection for 10080
Handling connection for 10080
Handling connection for 10080
Handling connection for 10080
Handling connection for 10080

Welcome to Cloud Shell! Type "help" to get started.
Your Cloud Platform project in this session is set to qwiklabs-gcp-03-eb0de0cb52ee.
Use “gcloud config set project [PROJECT_ID]” to change to a different project.
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ curl http://127.0.0.1:10080
{"message":"Hello"}
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ curl http://127.0.0.1:10080/secure
authorization failed
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ curl -u user http://127.0.0.1:10080/login
Enter host password for user 'user':
{"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InVzZXJAZXhhbXBsZS5jb20iLCJleHAiOjE2MTk0MTI3ODUsImlhdCI6MTYxOTE1MzU4NSwiaXNzIjoiYXV0aC5zZXJ2aWNlIiwic3ViIjoidXNlciJ9.PqIWT31DjOqvfzl-xoyCOpuywdLq09rT7bItLKBxFzA"}
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ TOKEN=$(curl http://127.0.0.1:10080/login -u user|jq -r '.token')
Enter host password for user 'user':
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   222  100   222    0     0    212      0  0:00:01  0:00:01 --:--:--   213
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ curl -H "Authorization: Bearer $TOKEN" http://127.0.0.1:10080/secure
{"message":"Hello"}
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl logs monolith
2021/04/23 04:51:48 Starting server...
2021/04/23 04:51:48 Health service listening on 0.0.0.0:81
2021/04/23 04:51:48 HTTP service listening on 0.0.0.0:80
127.0.0.1:54326 - - [Fri, 23 Apr 2021 04:52:27 UTC] "GET / HTTP/1.1" curl/7.64.0
127.0.0.1:54348 - - [Fri, 23 Apr 2021 04:52:36 UTC] "GET /secure HTTP/1.1" curl/7.64.0
127.0.0.1:54388 - - [Fri, 23 Apr 2021 04:53:05 UTC] "GET /login HTTP/1.1" curl/7.64.0
127.0.0.1:54436 - - [Fri, 23 Apr 2021 04:53:29 UTC] "GET /login HTTP/1.1" curl/7.64.0
127.0.0.1:54448 - - [Fri, 23 Apr 2021 04:53:35 UTC] "GET /secure HTTP/1.1" curl/7.64.0
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl logs -f monolith
2021/04/23 04:51:48 Starting server...
2021/04/23 04:51:48 Health service listening on 0.0.0.0:81
2021/04/23 04:51:48 HTTP service listening on 0.0.0.0:80
127.0.0.1:54326 - - [Fri, 23 Apr 2021 04:52:27 UTC] "GET / HTTP/1.1" curl/7.64.0
127.0.0.1:54348 - - [Fri, 23 Apr 2021 04:52:36 UTC] "GET /secure HTTP/1.1" curl/7.64.0
127.0.0.1:54388 - - [Fri, 23 Apr 2021 04:53:05 UTC] "GET /login HTTP/1.1" curl/7.64.0
127.0.0.1:54436 - - [Fri, 23 Apr 2021 04:53:29 UTC] "GET /login HTTP/1.1" curl/7.64.0
127.0.0.1:54448 - - [Fri, 23 Apr 2021 04:53:35 UTC] "GET /secure HTTP/1.1" curl/7.64.0
127.0.0.1:54480 - - [Fri, 23 Apr 2021 04:53:56 UTC] "GET / HTTP/1.1" curl/7.64.0




127.0.0.1:54494 - - [Fri, 23 Apr 2021 04:54:02 UTC] "GET / HTTP/1.1" curl/7.64.0
^C
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ^C
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ^C
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ^C
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ curl -k https://34.123.64.7:31000
curl: (7) Failed to connect to 34.123.64.7 port 31000: Connection refused
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get services monolith
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)         AGE
monolith   NodePort   10.3.248.193   <none>        443:31000/TCP   94s
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl describe services monolith
Name:                     monolith
Namespace:                default
Labels:                   <none>
Annotations:              <none>
Selector:                 app=monolith,secure=enabled
Type:                     NodePort
IP Families:              <none>
IP:                       10.3.248.193
IPs:                      <none>
Port:                     <unset>  443/TCP
TargetPort:               443/TCP
NodePort:                 <unset>  31000/TCP
Endpoints:                <none>
Session Affinity:         None
External Traffic Policy:  Cluster
Events:                   <none>
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get pods -l "app=monolith"
NAME              READY   STATUS    RESTARTS   AGE
monolith          1/1     Running   0          6m33s
secure-monolith   2/2     Running   0          3m17s
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get pods -l "app=monolith,secure=enabled"
No resources found in default namespace.
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl label pods secure-monolith 'secure=enabled'
pod/secure-monolith labeled
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get pods secure-monolith --show-labels
NAME              READY   STATUS    RESTARTS   AGE     LABELS
secure-monolith   2/2     Running   0          3m43s   app=monolith,secure=enabled
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl describe services monolith | grep Endpoints
Endpoints:                10.0.2.5:443
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ gcloud compute instances list
NAME                               ZONE           MACHINE_TYPE  PREEMPTIBLE  INTERNAL_IP  EXTERNAL_IP    STATUS
gke-io-default-pool-ff1906d4-n2hx  us-central1-b  e2-medium                  10.128.0.2   34.123.64.7    RUNNING
gke-io-default-pool-ff1906d4-pdk8  us-central1-b  e2-medium                  10.128.0.3   34.66.49.110   RUNNING
gke-io-default-pool-ff1906d4-s6l2  us-central1-b  e2-medium                  10.128.0.4   35.192.135.58  RUNNING
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$  curl -k https://34.123.64.7:31000
{"message":"Hello"}
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ cat deployments/auth.yaml
cat: deployments/auth.yaml: No such file or directory
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
orchestrate-with-kubernetes  README-cloudshell.txt
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ cd orchestrate-with-kubernetes/
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
cleanup.sh  CONTRIBUTING.md  kubernetes  labs  LICENSE  README.md
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ cd kubernetes/
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ ls
cleanup.sh  deployments  nginx  pods  services  tls
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ cat deployments/auth.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: auth
spec:
  selector:
    matchLabels:
      app: auth
  replicas: 1
  template:
    metadata:
      labels:
        app: auth
        track: stable
    spec:
      containers:
        - name: auth
          image: "kelseyhightower/auth:2.0.0"
          ports:
            - name: http
              containerPort: 80
            - name: health
              containerPort: 81
          resources:
            limits:
              cpu: 0.2
              memory: "10Mi"
          livenessProbe:
            httpGet:
              path: /healthz
              port: 81
              scheme: HTTP
            initialDelaySeconds: 5
            periodSeconds: 15
            timeoutSeconds: 5
          readinessProbe:
            httpGet:
              path: /readiness
              port: 81
              scheme: HTTP
            initialDelaySeconds: 5
            timeoutSeconds: 1
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f deployments/auth.yaml
deployment.apps/auth created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f services/auth.yaml
service/auth created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f deployments/hello.yaml
deployment.apps/hello created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f services/hello.yaml
service/hello created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create configmap nginx-frontend-conf --from-file=nginx/frontend.conf
configmap/nginx-frontend-conf created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f deployments/frontend.yaml
deployment.apps/frontend created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f services/frontend.yaml
service/frontend created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get services frontend
NAME       TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)         AGE
frontend   LoadBalancer   10.3.254.146   <pending>     443:32650/TCP   23s
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl get services frontend
NAME       TYPE           CLUSTER-IP     EXTERNAL-IP   PORT(S)         AGE
frontend   LoadBalancer   10.3.254.146   34.71.4.72    443:32650/TCP   30s
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ curl -k https://34.71.4.72

student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ curl http://127.0.0.1:10080
{"message":"Hello"}
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ curl http://127.0.0.1:10080
{"message":"Hello"}
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl exec monolith --stdin --tty -c monolith /bin/sh
kubectl exec [POD] [COMMAND] is DEPRECATED and will be removed in a future version. Use kubectl exec [POD] -- [COMMAND] instead.
/ # ping -c 3 google.com
PING google.com (172.217.219.139): 56 data bytes
64 bytes from 172.217.219.139: seq=0 ttl=114 time=1.179 ms
64 bytes from 172.217.219.139: seq=1 ttl=114 time=1.221 ms
64 bytes from 172.217.219.139: seq=2 ttl=114 time=1.190 ms

--- google.com ping statistics ---
3 packets transmitted, 3 packets received, 0% packet loss
round-trip min/avg/max = 1.179/1.196/1.221 ms
/ # exit
student_03_e637940a35a5@cloudshell:~ (qwiklabs-gcp-03-eb0de0cb52ee)$ cd ~/orchestrate-with-kubernetes/kubernetes
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ cat pods/secure-monolith.yaml
apiVersion: v1
kind: Pod
metadata:
  name: "secure-monolith"
  labels:
    app: monolith
spec:
  containers:
    - name: nginx
      image: "nginx:1.9.14"
      lifecycle:
        preStop:
          exec:
            command: ["/usr/sbin/nginx","-s","quit"]
      volumeMounts:
        - name: "nginx-proxy-conf"
          mountPath: "/etc/nginx/conf.d"
        - name: "tls-certs"
          mountPath: "/etc/tls"
    - name: monolith
      image: "kelseyhightower/monolith:1.0.0"
      ports:
        - name: http
          containerPort: 80
        - name: health
          containerPort: 81
      resources:
        limits:
          cpu: 0.2
          memory: "10Mi"
      livenessProbe:
        httpGet:
          path: /healthz
          port: 81
          scheme: HTTP
        initialDelaySeconds: 5
        periodSeconds: 15
        timeoutSeconds: 5
      readinessProbe:
        httpGet:
          path: /readiness
          port: 81
          scheme: HTTP
        initialDelaySeconds: 5
        timeoutSeconds: 1
  volumes:
    - name: "tls-certs"
      secret:
        secretName: "tls-certs"
    - name: "nginx-proxy-conf"
      configMap:
        name: "nginx-proxy-conf"
        items:
          - key: "proxy.conf"
            path: "proxy.conf"
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create secret generic tls-certs --from-file tls/
secret/tls-certs created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create configmap nginx-proxy-conf --from-file nginx/proxy.conf
configmap/nginx-proxy-conf created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f pods/secure-monolith.yaml

pod/secure-monolith created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ cat services/monolith.yaml
kind: Service
apiVersion: v1
metadata:
  name: "monolith"
spec:
  selector:
    app: "monolith"
    secure: "enabled"
  ports:
    - protocol: "TCP"
      port: 443
      targetPort: 443
      nodePort: 31000
  type: NodePort
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ kubectl create -f services/monolith.yaml
service/monolith created
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ gcloud compute firewall-rules create allow-monolith-nodeport \
>   --allow=tcp:31000
Creating firewall...⠹Created [https://www.googleapis.com/compute/v1/projects/qwiklabs-gcp-03-eb0de0cb52ee/global/firewalls/allow-monolith-nodeport].
Creating firewall...done.
NAME                     NETWORK  DIRECTION  PRIORITY  ALLOW      DENY  DISABLED
allow-monolith-nodeport  default  INGRESS    1000      tcp:31000        False
student_03_e637940a35a5@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-03-eb0de0cb52ee)$ gcloud compute instances list
NAME                               ZONE           MACHINE_TYPE  PREEMPTIBLE  INTERNAL_IP  EXTERNAL_IP    STATUS
gke-io-default-pool-ff1906d4-n2hx  us-central1-b  e2-medium                  10.128.0.2   34.123.64.7    RUNNING
gke-io-default-pool-ff1906d4-pdk8  us-central1-b  e2-medium                  10.128.0.3   34.66.49.110   RUNNING
```



Managing Deployments Using Kubernetes Engine
Dev Ops best practices make use of multiple deployments to manage application deployment scenarios. This lab provides practice in scaling and managing containers to accomplish common scenarios where multiple heterogeneous deployments are used.
Continuous Delivery with Jenkins in Kubernetes Engine
In this lab you will deploy and completely configure a continuous delivery pipeline using Jenkins running on Kubernetes Engine and go through the dev - deploy process.
Deploy to Kubernetes in Google Cloud: Challenge Lab
This challenge lab tests your skills and knowledge from the labs in the Kubernetes in Google Cloud quest. You should be familiar with the content of the labs before attempting this lab.
