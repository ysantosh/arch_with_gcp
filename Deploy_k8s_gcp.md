Introduction to Docker
In this lab you will familiarize yourself with the basic Docker container environment commands. You will create, run, and debug containers, and learn to pull and push images to and from Google Container Registry.
Kubernetes Engine: Qwik Start
Google Kubernetes Engine provides a managed environment for deploying, managing, and scaling your containerized applications using Google infrastructure. This hands-on lab shows you how deploy a containerized application with Kubernetes Engine. Watch the short video Manage Containerized Apps with Kubernetes Engine.
Orchestrating the Cloud with Kubernetes
In this lab you will learn how to provision a complete Kubernetes cluster using Google Container Engine; deploy and manage Docker containers using kubectl; and break an application into microservices using Kubernetes’ Deployments and Services.
https://github.com/googlecodelabs/orchestrate-with-kubernetes

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
```
gcloud auth list
gcloud config set compute/zone us-central1-a
gsutil -m cp -r gs://spls/gsp053/orchestrate-with-kubernetes .
cd orchestrate-with-kubernetes/kubernetes
gcloud container clusters create bootcamp --num-nodes 5 --scopes "https://www.googleapis.com/auth/projecthosting,storage-rw"
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ gcloud container clusters create bootcamp --num-nodes 5 --scopes "https://www.googleapis.com/auth/projecthosting,storage-rw"
WARNING: Starting in January 2021, clusters will use the Regular release channel by default when `--cluster-version`, `--release-channel`, `--no-enable-autoupgrade`, and `--no-enable-autorepair` flags are not specified.
WARNING: Currently VPC-native is not the default mode during cluster creation. In the future, this will become the default mode and can be disabled using `--no-enable-ip-alias` flag. Use `--[no-]enable-ip-alias` flag to suppress this warning.
WARNING: Starting with version 1.18, clusters will have shielded GKE nodes by default.
WARNING: Your Pod address range (`--cluster-ipv4-cidr`) can accommodate at most 1008 node(s).
WARNING: Starting with version 1.19, newly created clusters and node-pools will have COS_CONTAINERD as the default node image when no image type is specified.
Creating cluster bootcamp in us-central1-a... Cluster is being health-checked (master is healthy)...done.
Created [https://container.googleapis.com/v1/projects/qwiklabs-gcp-00-6eac7c658b13/zones/us-central1-a/clusters/bootcamp].
To inspect the contents of your cluster, go to: https://console.cloud.google.com/kubernetes/workload_/gcloud/us-central1-a/bootcamp?project=qwiklabs-gcp-00-6eac7c658b13
kubeconfig entry generated for bootcamp.
NAME      LOCATION       MASTER_VERSION   MASTER_IP      MACHINE_TYPE  NODE_VERSION     NUM_NODES  STATUS
bootcamp  us-central1-a  1.18.16-gke.502  35.223.114.83  e2-medium     1.18.16-gke.502  5          RUNNING
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl explain deployment
KIND:     Deployment
VERSION:  apps/v1

DESCRIPTION:
     Deployment enables declarative updates for Pods and ReplicaSets.

FIELDS:
   apiVersion   <string>
     APIVersion defines the versioned schema of this representation of an
     object. Servers should convert recognized schemas to the latest internal
     value, and may reject unrecognized values. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#resources

   kind <string>
     Kind is a string value representing the REST resource this object
     represents. Servers may infer this from the endpoint the client submits
     requests to. Cannot be updated. In CamelCase. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#types-kinds

   metadata     <Object>
     Standard object metadata.

   spec <Object>
     Specification of the desired behavior of the Deployment.

   status       <Object>
     Most recently observed status of the Deployment.
     


kubectl explain deployment --recursive

student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl explain deployment.metadata.name
KIND:     Deployment
VERSION:  apps/v1

FIELD:    name <string>

DESCRIPTION:
     Name must be unique within a namespace. Is required when creating
     resources, although some resources may allow a client to request the
     generation of an appropriate name automatically. Name is primarily intended
     for creation idempotence and configuration definition. Cannot be updated.
     More info: http://kubernetes.io/docs/user-guide/identifiers#names
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ vi deployments/auth.yaml
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create -f deployments/auth.yaml
deployment.apps/auth created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get deployments
NAME   READY   UP-TO-DATE   AVAILABLE   AGE
auth   0/1     1            0           7s
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get replicasets
NAME              DESIRED   CURRENT   READY   AGE
auth-7cffdb8677   1         1         0       11s
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get pods
NAME                    READY   STATUS    RESTARTS   AGE
auth-7cffdb8677-5vptx   1/1     Running   0          19s
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create -f services/auth.yaml
service/auth created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create -f deployments/hello.yaml
deployment.apps/hello created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create -f services/hello.yaml
service/hello created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create secret generic tls-certs --from-file tls/
secret/tls-certs created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create configmap nginx-frontend-conf --from-file=nginx/frontend.conf
configmap/nginx-frontend-conf created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create -f deployments/frontend.yaml
deployment.apps/frontend created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create -f services/frontend.yaml
service/frontend created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get services frontend
NAME       TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)         AGE
frontend   LoadBalancer   10.115.247.104   <pending>     443:32107/TCP   25s
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ curl -ks https://
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get services frontend
NAME       TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)         AGE
frontend   LoadBalancer   10.115.247.104   34.72.3.228   443:32107/TCP   41s
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ curl -ks https://34.72.3.228
{"message":"Hello"}
curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`
{"message":"Hello"}
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl explain deployment.spec.replicas
KIND:     Deployment
VERSION:  apps/v1

FIELD:    replicas <integer>

DESCRIPTION:
     Number of desired pods. This is a pointer to distinguish between explicit
     zero and not specified. Defaults to 1.
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl scale deployment hello --replicas=5
deployment.apps/hello scaled
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get pods | grep hello- | wc -l
5
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl scale deployment hello --replicas=3
deployment.apps/hello scaled
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get pods | grep hello- | wc -l
4
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get pods | grep hello- | wc -l
3

student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl edit deployment hello
deployment.apps/hello edited
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get replicaset
NAME                  DESIRED   CURRENT   READY   AGE
auth-7cffdb8677       1         1         1       4m22s
frontend-7b4b97c4dc   1         1         1       3m38s
hello-687bb4b8f4      2         2         2       3m52s
hello-d99c798f        2         2         1       9s
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl rollout history deployment/hello
deployment.apps/hello
REVISION  CHANGE-CAUSE
1         <none>
2         <none>

student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl rollout pause deployment/hello
deployment.apps/hello paused
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl rollout status deployment/hello
deployment "hello" successfully rolled out
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get pods -o jsonpath --template='{range .items[*]}{.metadata.name}{"\t"}{"\t"}{.spec.containers[0].image}{"\n"}{end}'
auth-7cffdb8677-5vptx           kelseyhightower/auth:1.0.0
frontend-7b4b97c4dc-kg65m               nginx:1.9.14
hello-d99c798f-2qvrf            kelseyhightower/hello:2.0.0
hello-d99c798f-xmxsv            kelseyhightower/hello:2.0.0
hello-d99c798f-xtgf7            kelseyhightower/hello:2.0.0
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl rollout resume deployment/hello
deployment.apps/hello resumed
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl rollout status deployment/hello
deployment "hello" successfully rolled out
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl rollout undo deployment/hello
deployment.apps/hello rolled back
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl rollout history deployment/hello
deployment.apps/hello
REVISION  CHANGE-CAUSE
2         <none>
3         <none>

student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get pods -o jsonpath --template='{range .items[*]}{.metadata.name}{"\t"}{"\t"}{.spec.containers[0].image}{"\n"}{end}'
auth-7cffdb8677-5vptx           kelseyhightower/auth:1.0.0
frontend-7b4b97c4dc-kg65m               nginx:1.9.14
hello-687bb4b8f4-h8sv8          kelseyhightower/hello:1.0.0
hello-687bb4b8f4-vh6pc          kelseyhightower/hello:1.0.0
hello-d99c798f-2qvrf            kelseyhightower/hello:2.0.0
hello-d99c798f-xtgf7            kelseyhightower/hello:2.0.0

student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ cat deployments/hello-canary.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-canary
spec:
  replicas: 1
  selector:
    matchLabels:
      app: hello
  template:
    metadata:
      labels:
        app: hello
        track: canary
        version: 2.0.0
    spec:
      containers:
        - name: hello
          image: kelseyhightower/hello:2.0.0
          ports:
            - name: http
              containerPort: 80
            - name: health
              containerPort: 81
          resources:
            limits:
              cpu: 0.2
              memory: 10Mi
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
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create -f deployments/hello-canary.yaml
deployment.apps/hello-canary created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl get deployments
NAME           READY   UP-TO-DATE   AVAILABLE   AGE
auth           1/1     1            1           6m48s
frontend       1/1     1            1           6m4s
hello          3/3     3            3           6m18s
hello-canary   0/1     1            0           5s
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`/version
{"version":"1.0.0"}
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl apply -f services/hello-blue.yaml
Warning: resource services/hello is missing the kubectl.kubernetes.io/last-applied-configuration annotation which is required by kubectl apply. kubectl apply should only be used on resources created declaratively by either kubectl create --save-config or kubectl apply. The missing annotation will be patched automatically.
service/hello configured
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl create -f deployments/hello-green.yaml
deployment.apps/hello-green created
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`/version
{"version":"1.0.0"}
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl apply -f services/hello-green.yaml
service/hello configured
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`/version
{"version":"2.0.0"}
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl explain deploymentKIND:     Deployment
VERSION:  apps/v1

DESCRIPTION:
     Deployment enables declarative updates for Pods and ReplicaSets.

FIELDS:
   apiVersion   <string>
     APIVersion defines the versioned schema of this representation of an
     object. Servers should convert recognized schemas to the latest internal
     value, and may reject unrecognized values. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#resources

   kind <string>
     Kind is a string value representing the REST resource this object
     represents. Servers may infer this from the endpoint the client submits
     requests to. Cannot be updated. In CamelCase. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#types-kinds

   metadata     <Object>
     Standard object metadata.

   spec <Object>
     Specification of the desired behavior of the Deployment.

   status       <Object>
     Most recently observed status of the Deployment.

student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ kubectl apply -f services/hello-blue.yamlservice/hello configured
student_00_6cb649057f82@cloudshell:~/orchestrate-with-kubernetes/kubernetes (qwiklabs-gcp-00-6eac7c658b13)$ curl -ks https://`kubectl get svc frontend -o=jsonpath="{.status.loadBalancer.ingress[0].ip}"`/version
{"version":"1.0.0"}


```

Continuous Delivery with Jenkins in Kubernetes Engine
In this lab you will deploy and completely configure a continuous delivery pipeline using Jenkins running on Kubernetes Engine and go through the dev - deploy process.

```
student_03_cab8fcbc3799@cloudshell:~ (qwiklabs-gcp-03-919c526475cd)$ gcloud auth list
           Credentialed Accounts
ACTIVE  ACCOUNT
*       student-03-cab8fcbc3799@qwiklabs.net

To set the active account, run:
    $ gcloud config set account `ACCOUNT`

student_03_cab8fcbc3799@cloudshell:~ (qwiklabs-gcp-03-919c526475cd)$ gcloud config set compute/zone us-east1-d
Updated property [compute/zone].
student_03_cab8fcbc3799@cloudshell:~ (qwiklabs-gcp-03-919c526475cd)$ git clone https://github.com/GoogleCloudPlatform/continuous-deployment-on-kubernetes.git
Cloning into 'continuous-deployment-on-kubernetes'...
remote: Enumerating objects: 941, done.
remote: Total 941 (delta 0), reused 0 (delta 0), pack-reused 941
Receiving objects: 100% (941/941), 1.91 MiB | 1.98 MiB/s, done.
Resolving deltas: 100% (463/463), done.
student_03_cab8fcbc3799@cloudshell:~ (qwiklabs-gcp-03-919c526475cd)$ cd continuous-deployment-on-kubernetes
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ gcloud container clusters create jenkins-cd \
> --num-nodes 2 \
> --machine-type n1-standard-2 \
> --scopes "https://www.googleapis.com/auth/source.read_write,cloud-platform"
WARNING: Starting in January 2021, clusters will use the Regular release channel by default when `--cluster-version`, `--release-channel`, `--no-enable-autoupgrade`, and `--no-enable-autorepair` flags are not specified.
WARNING: Currently VPC-native is not the default mode during cluster creation. In the future, this will become the default mode and can be disabled using `--no-enable-ip-alias` flag. Use `--[no-]enable-ip-alias` flag to suppress this warning.
WARNING: Starting with version 1.18, clusters will have shielded GKE nodes by default.
WARNING: Your Pod address range (`--cluster-ipv4-cidr`) can accommodate at most 1008 node(s).
WARNING: Starting with version 1.19, newly created clusters and node-pools will have COS_CONTAINERD as the default node image when no image type is specified.
Creating cluster jenkins-cd in us-east1-d... Cluster is being health-checked (master is healthy)...done.                                                                                                 
Created [https://container.googleapis.com/v1/projects/qwiklabs-gcp-03-919c526475cd/zones/us-east1-d/clusters/jenkins-cd].
To inspect the contents of your cluster, go to: https://console.cloud.google.com/kubernetes/workload_/gcloud/us-east1-d/jenkins-cd?project=qwiklabs-gcp-03-919c526475cd
kubeconfig entry generated for jenkins-cd.
NAME        LOCATION    MASTER_VERSION   MASTER_IP       MACHINE_TYPE   NODE_VERSION     NUM_NODES  STATUS
jenkins-cd  us-east1-d  1.18.16-gke.502  35.243.128.105  n1-standard-2  1.18.16-gke.502  2          RUNNING
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ gcloud container clusters list
NAME        LOCATION    MASTER_VERSION   MASTER_IP       MACHINE_TYPE   NODE_VERSION     NUM_NODES  STATUS
jenkins-cd  us-east1-d  1.18.16-gke.502  35.243.128.105  n1-standard-2  1.18.16-gke.502  2          RUNNING
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ gcloud container clusters get-credentials jenkins-cd
Fetching cluster endpoint and auth data.
kubeconfig entry generated for jenkins-cd.
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ kubectl cluster-info
Kubernetes control plane is running at https://35.243.128.105
GLBCDefaultBackend is running at https://35.243.128.105/api/v1/namespaces/kube-system/services/default-http-backend:http/proxy
KubeDNS is running at https://35.243.128.105/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
Metrics-server is running at https://35.243.128.105/api/v1/namespaces/kube-system/services/https:metrics-server:/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ helm repo add jenkins https://charts.jenkins.io
"jenkins" has been added to your repositories
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "jenkins" chart repository
Update Complete. ⎈Happy Helming!⎈
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ helm install cd jenkins/jenkins -f jenkins/values.yaml --version 1.2.2 --wait
NAME: cd
LAST DEPLOYED: Fri Apr 23 05:40:56 2021
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
1.printfo$(kubectl'getesecretw--namespaceidefault cd-jenkins -o jsonpath="{.data.jenkins-admin-password}" | base64 --decode);echo
ForLmorelinformationsonorunningoJenkinsaoneKubernetes,evisit:npp.kubernetes.io/component=jenkins-master" -l "app.kubernetes.io/instance=cd" -o jsonpath="{.items[0].metadata.name}")
https://cloud.google.com/solutions/jenkins-on-container-engine

student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ kubectl get pods
NAME                          READY   STATUS    RESTARTS   AGE
cd-jenkins-775588cddf-64kvv   1/1     Running   0          2m43s
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ kubectl create clusterrolebinding jenkins-deploy --clusterrole=cluster-admin --serviceaccount=default:cd-jenkins
clusterrolebinding.rbac.authorization.k8s.io/jenkins-deploy created
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ clusterrolebinding.rbac.authorization.k8s.io/jenkins-deploy created
-bash: clusterrolebinding.rbac.authorization.k8s.io/jenkins-deploy: No such file or directory
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/component=jenkins-master-l "app.kubernetes.io/instance=cd" -o jsonpath="{.items[0].metadata.name}")
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ kubectl port-forward $POD_NAME 8080:8080 >> /dev/null &
[1] 1449
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ kubectl get svc
NAME               TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)     AGE
cd-jenkins         ClusterIP   10.3.245.206   <none>        8080/TCP    3m20s
cd-jenkins-agent   ClusterIP   10.3.240.164   <none>        50000/TCP   3m20s
kubernetes         ClusterIP   10.3.240.1     <none>        443/TCP     5m17s
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ printf $(kubectl get secret cd-jenkins -o jsonpath="{.data.jenkins-admin-password}" | base64 --decode);echo
JHA4L3X5D9
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes (qwiklabs-gcp-03-919c526475cd)$ cd sample-app
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl create ns production
namespace/production created
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl apply -f k8s/production -n production
deployment.apps/gceme-backend-production created
deployment.apps/gceme-frontend-production created
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl apply -f k8s/canary -n production
deployment.apps/gceme-backend-canary created
deployment.apps/gceme-frontend-canary created
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl apply -f k8s/services -n production
service/gceme-backend created
service/gceme-frontend created
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl scale deployment gceme-frontend-production -n production --replicas 4
deployment.apps/gceme-frontend-production scaled
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl get pods -n production -l app=gceme -l role=frontend
NAME                                         READY   STATUS    RESTARTS   AGE
gceme-frontend-canary-67f5ffdcdd-hchxh       0/1     Running   0          24s
gceme-frontend-production-5f9dc74dfc-559fx   0/1     Running   0          5s
gceme-frontend-production-5f9dc74dfc-ltpnq   0/1     Running   0          5s
gceme-frontend-production-5f9dc74dfc-pt89w   0/1     Running   0          5s
gceme-frontend-production-5f9dc74dfc-w2pgv   0/1     Running   0          30s
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl get pods -n production -l app=gceme -l role=backend
NAME                                        READY   STATUS    RESTARTS   AGE
gceme-backend-canary-76f8f78894-d7smq       1/1     Running   0          30s
gceme-backend-production-5c59b5bdcc-rk8w7   1/1     Running   0          37s
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl get service gceme-frontend -n production
NAME             TYPE           CLUSTER-IP    EXTERNAL-IP   PORT(S)        AGE
gceme-frontend   LoadBalancer   10.3.244.62   <pending>     80:31684/TCP   39s
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl get service gceme-frontend -n production
NAME             TYPE           CLUSTER-IP    EXTERNAL-IP     PORT(S)        AGE
gceme-frontend   LoadBalancer   10.3.244.62   35.237.27.108   80:31684/TCP   75s
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ export FRONTEND_SERVICE_IP=$(kubectl get -o jsonpath="{.status.loadBalancer.ingress[0].ip}--namespace=production services gceme-frontend)
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ curl http://$FRONTEND_SERVICE_IP/version
1.0.0
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ gcloud source repos create default
Created [default].
WARNING: You may be billed for this repository. See https://cloud.google.com/source-repositories/docs/pricing for details.
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git init
Initialized empty Git repository in /home/student_03_cab8fcbc3799/continuous-deployment-on-kubernetes/sample-app/.git/
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config credential.helper gcloud.sh
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git remote add origin https://source.developers.google.com/p/$DEVSHELL_PROJECT_ID/r/default
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global user.email student-03-cab8fcbc3799@qwiklabs.net
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global username student-03-cab8fcbc3799@qwiklabs.ne
error: key does not contain a section: username
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git add .
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git commit -m "Initial commit"

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: empty ident name (for <student-03-cab8fcbc3799@qwiklabs.net>) not allowed
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global user.email student-03-cab8fcbc3799@qwiklabs.net
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global user.name "student-03-cab8fcbc3799"
student_03_cab8f^C
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ ^C
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git commit -m "Initial commit"
[master (root-commit) 73dcc86] Initial commit
 31 files changed, 2470 insertions(+)
 create mode 100644 Dockerfile
 create mode 100644 Gopkg.lock
 create mode 100644 Gopkg.toml
 create mode 100644 Jenkinsfile
 create mode 100644 html.go
 create mode 100644 k8s/canary/backend-canary.yaml
 create mode 100644 k8s/canary/frontend-canary.yaml
 create mode 100644 k8s/dev/backend-dev.yaml
 create mode 100644 k8s/dev/default.yml
 create mode 100644 k8s/dev/frontend-dev.yaml
 create mode 100644 k8s/production/backend-production.yaml
 create mode 100644 k8s/production/frontend-production.yaml
 create mode 100644 k8s/services/backend.yaml
 create mode 100644 k8s/services/frontend.yaml
 create mode 100644 main.go
 create mode 100644 main_test.go
 create mode 100644 vendor/cloud.google.com/go/AUTHORS
 create mode 100644 vendor/cloud.google.com/go/CONTRIBUTORS
 create mode 100644 vendor/cloud.google.com/go/LICENSE
 create mode 100644 vendor/cloud.google.com/go/compute/metadata/metadata.go
 create mode 100644 vendor/golang.org/x/net/AUTHORS
 create mode 100644 vendor/golang.org/x/net/CONTRIBUTORS
 create mode 100644 vendor/golang.org/x/net/LICENSE
 create mode 100644 vendor/golang.org/x/net/PATENTS
 create mode 100644 vendor/golang.org/x/net/context/context.go
 create mode 100644 vendor/golang.org/x/net/context/ctxhttp/ctxhttp.go
 create mode 100644 vendor/golang.org/x/net/context/ctxhttp/ctxhttp_pre17.go
 create mode 100644 vendor/golang.org/x/net/context/go17.go
 create mode 100644 vendor/golang.org/x/net/context/go19.go
 create mode 100644 vendor/golang.org/x/net/context/pre_go17.go
 create mode 100644 vendor/golang.org/x/net/context/pre_go19.go
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git push origin master
Enumerating objects: 48, done.
Counting objects: 100% (48/48), done.
Delta compression using up to 2 threads
Compressing objects: 100% (43/43), done.
Writing objects: 100% (48/48), 27.23 KiB | 3.02 MiB/s, done.
Total 48 (delta 11), reused 0 (delta 0)
remote: Resolving deltas: 100% (11/11)
To https://source.developers.google.com/p/qwiklabs-gcp-03-919c526475cd/r/default
 * [new branch]      master -> master

-919c526475cd)$ kubectl get service gceme-frontend -n production
NAME             TYPE           CLUSTER-IP    EXTERNAL-IP     PORT(S)        AGE
gceme-frontend   LoadBalancer   10.3.244.62   35.237.27.108   80:31684/TCP   75s
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ export FRONTEND_SERVICE_IP=$(kubectl get -o jsonpath="{.status.loadBalancer.ingress[0].ip}" --namespace=production services gceme-frontend)
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ curl http://$FRONTEND_SERVICE_IP/version
1.0.0
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ gcloud source repos create default
Created [default].
WARNING: You may be billed for this repository. See https://cloud.google.com/source-repositories/docs/pricing for details.
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git init
Initialized empty Git repository in /home/student_03_cab8fcbc3799/continuous-deployment-on-kubernetes/sample-app/.git/
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config credential.helper gcloud.sh
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git remote add origin https://source.developers.google.com/p/$DEVSHELL_PROJECT_ID/r/defaul
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global user.email student-03-cab8fcbc3799@qwiklabs.net
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global username student-03-cab8fcbc3799@qwiklabs.ne
error: key does not contain a section: username
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git add .
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git commit -m "Initial commit"

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: empty ident name (for <student-03-cab8fcbc3799@qwiklabs.net>) not allowed
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global user.email student-03-cab8fcbc3799@qwiklabs.net                 
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
····································································································
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global user.email student-03-cab8fcbc3799@qwiklabs.net                 
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git config --global user.name "student-03-cab8fcbc3799"                             
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ ^C
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ ^C
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git commit -m "Initial commit"
pipeline {
[master (root-commit) 73dcc86] Initial commit
 31 files changed, 2470 insertions(+)
 create mode 100644 Dockerfile
 create mode 100644 Gopkg.lock
 create mode 100644 Gopkg.toml
 create mode 100644 Jenkinsfile
 create mode 100644 html.go
 create mode 100644 k8s/canary/backend-canary.yaml
 create mode 100644 k8s/canary/frontend-canary.yaml
 create mode 100644 k8s/dev/backend-dev.yaml
 create mode 100644 k8s/dev/default.yml
 create mode 100644 k8s/dev/frontend-dev.yaml
 create mode 100644 k8s/production/backend-production.yaml
 create mode 100644 k8s/production/frontend-production.yaml
 create mode 100644 k8s/services/backend.yaml
 create mode 100644 k8s/services/frontend.yaml
 create mode 100644 main.go
 create mode 100644 main_test.go
 create mode 100644 vendor/cloud.google.com/go/AUTHORS
 create mode 100644 vendor/cloud.google.com/go/CONTRIBUTORS
 create mode 100644 vendor/cloud.google.com/go/LICENSE
 create mode 100644 vendor/cloud.google.com/go/compute/metadata/metadata.go
 create mode 100644 vendor/golang.org/x/net/AUTHORS
 create mode 100644 vendor/golang.org/x/net/CONTRIBUTORS
 create mode 100644 vendor/golang.org/x/net/LICENSE
 create mode 100644 vendor/golang.org/x/net/PATENTS
 create mode 100644 vendor/golang.org/x/net/context/context.go
 create mode 100644 vendor/golang.org/x/net/context/ctxhttp/ctxhttp.go
 create mode 100644 vendor/golang.org/x/net/context/ctxhttp/ctxhttp_pre17.go
 create mode 100644 vendor/golang.org/x/net/context/go17.go
 create mode 100644 vendor/golang.org/x/net/context/go19.go
 create mode 100644 vendor/golang.org/x/net/context/pre_go17.go
 create mode 100644 vendor/golang.org/x/net/context/pre_go19.go
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git push origin master
Enumerating objects: 48, done.
Counting objects: 100% (48/48), done.
Delta compression using up to 2 threads
Compressing objects: 100% (43/43), done.
Writing objects: 100% (48/48), 27.23 KiB | 3.02 MiB/s, done.
Total 48 (delta 11), reused 0 (delta 0)
remote: Resolving deltas: 100% (11/11)
To https://source.developers.google.com/p/qwiklabs-gcp-03-919c526475cd/r/default
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git checkout -b new-feature
Switched to a new branch 'new-feature'
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ vi Jenkinsfile
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ cat Jenkinsfile
pipeline {

  environment {
    PROJECT = "qwiklabs-gcp-03-919c526475cd"
    APP_NAME = "gceme"
    FE_SVC_NAME = "${APP_NAME}-frontend"
    CLUSTER = "jenkins-cd"
    CLUSTER_ZONE = "us-east1-d"
    IMAGE_TAG = "gcr.io/${PROJECT}/${APP_NAME}:${env.BRANCH_NAME}.${env.BUILD_NUMBER}"
    JENKINS_CRED = "${PROJECT}"
  }

  agent {
    kubernetes {
      label 'sample-app'
      defaultContainer 'jnlp'
      yaml """
apiVersion: v1
kind: Pod
metadata:
labels:
  component: ci
spec:
  # Use service account that can deploy to all namespaces
  serviceAccountName: cd-jenkins
  containers:
  - name: golang
    image: golang:1.10
    command:
    - cat
    tty: true
  - name: gcloud
    image: gcr.io/cloud-builders/gcloud
    command:
    - cat
    tty: true
  - name: kubectl
    image: gcr.io/cloud-builders/kubectl
    command:
    - cat
    tty: true
"""
}
  }
  stages {
    stage('Test') {
      steps {
        container('golang') {
          sh """
            ln -s `pwd` /go/src/sample-app
            cd /go/src/sample-app
            go test
          """
        }
      }
    }
    stage('Build and push image with Container Builder') {
      steps {
        container('gcloud') {
          sh "PYTHONUNBUFFERED=1 gcloud builds submit -t ${IMAGE_TAG} ."
        }
      }
    }
    stage('Deploy Canary') {
      // Canary branch
      when { branch 'canary' }
      steps {
        container('kubectl') {
          // Change deployed image in canary to the one we just built
          sh("sed -i.bak 's#gcr.io/cloud-solutions-images/gceme:1.0.0#${IMAGE_TAG}#' ./k8s/canary/*.yaml")
          <td>{{.Hostname}}</td>          step([$class: 'KubernetesEngineBuilder', namespace:'production', projectId: env.PROJECT, clusterName: env.CLUSTER, zone: env.CLUSTER_ZONE, manifestPattern: 'k8s/services', credentialsId: env.JENKIN
# Licensed under the Apache License, Version 2.0 (the "License");
S_CRED, verifyDeployments: false])
          step([$class: 'KubernetesEngineBuilder', namespace:'production', projectId: env.PROJECT, clusterName: env.CLUSTER, zone: env.CLUSTER_ZONE, manifestPattern: 'k8s/canary', credentialsId: env.JENKINS_CRED, verifyDeployments: true])
          sh("echo http://`kubectl --namespace=production get service/${FE_SVC_NAME} -o jsonpath='{.status.loadBalancer.ingress[0].ip}'` > ${FE_SVC_NAME}")
        }
      }
    }
    stage('Deploy Production') {
      // Production branch
      when { branch 'master' }      steps{        container('kubectl') {        // Change deployed image in canary to the one we just built          sh("sed -i.bak 's#gcr.io/cloud-solutions-images/gceme:1.0.0#${IMAGE_TAG}#' ./k8s/production/*.yaml")
          """
        }
      }
    }
    stage('Build and push image with Container Builder') {
      steps {
        container('gcloud') {
          sh "PYTHONUNBUFFERED=1 gcloud builds submit -t ${IMAGE_TAG} ."
        }
      }
    }
    stage('Deploy Canary') {
      // Canary branch
      when { branch 'canary' }
      steps {
        container('kubectl') {
          // Change deployed image in canary to the one we just built
          sh("sed -i.bak 's#gcr.io/cloud-solutions-images/gceme:1.0.0#${IMAGE_TAG}#' ./k8s/canary/*.yaml")
          step([$class: 'KubernetesEngineBuilder', namespace:'production', projectId: env.PROJECT, clusterName: env.CLUSTER, zone: env.CLUSTER_ZONE, manifestPattern: 'k8s/services', credentialsId: env.JENKINS_CRED, verifyDeployments: false])
          step([$class: 'KubernetesEngineBuilder', namespace:'production', projectId: env.PROJECT, clusterName: env.CLUSTER, zone: env.CLUSTER_ZONE, manifestPattern: 'k8s/canary', credentialsId: env.JENKINS_CRED, verifyDeployments: true])
          sh("echo http://`kubectl --namespace=production get service/${FE_SVC_NAME} -o jsonpath='{.status.loadBalancer.ingress[0].ip}'` > ${FE_SVC_NAME}")
        }
      }
    }
    stage('Deploy Production') {
      // Production branch
      when { branch 'master' }
      steps{
        container('kubectl') {
        // Change deployed image in canary to the one we just built
          sh("sed -i.bak 's#gcr.io/cloud-solutions-images/gceme:1.0.0#${IMAGE_TAG}#' ./k8s/production/*.yaml")
          step([$class: 'KubernetesEngineBuilder', namespace:'production', projectId: env.PROJECT, clusterName: env.CLUSTER, zone: env.CLUSTER_ZONE, manifestPattern: 'k8s/services', credentialsId: env.JENKINS_CRED, verifyDeployments: false])
          step([$class: 'KubernetesEngineBuilder', namespace:'production', projectId: env.PROJECT, clusterName: env.CLUSTER, zone: env.CLUSTER_ZONE, manifestPattern: 'k8s/production', credentialsId: env.JENKINS_CRED, verifyDeployments: true])
          sh("echo http://`kubectl --namespace=production get service/${FE_SVC_NAME} -o jsonpath='{.status.loadBalancer.ingress[0].ip}'` > ${FE_SVC_NAME}")
        }
      }
    }
    stage('Deploy Dev') {
      // Developer Branches
      when {
        not { branch 'master' }
        not { branch 'canary' }
      }
      steps {
        container('kubectl') {
          // Create namespace if it doesn't exist
          sh("kubectl get ns ${env.BRANCH_NAME} || kubectl create ns ${env.BRANCH_NAME}")
          // Don't use public load balancing for development branches
          sh("sed -i.bak 's#LoadBalancer#ClusterIP#' ./k8s/services/frontend.yaml")
          sh("sed -i.bak 's#gcr.io/cloud-solutions-images/gceme:1.0.0#${IMAGE_TAG}#' ./k8s/dev/*.yaml")
          step([$class: 'KubernetesEngineBuilder', namespace: "${env.BRANCH_NAME}", projectId: env.PROJECT, clusterName: env.CLUSTER, zone: env.CLUSTER_ZONE, manifestPattern: 'k8s/services', credentialsId: env.JENKINS_CRED, verifyDeployments: false])
          step([$class: 'KubernetesEngineBuilder', namespace: "${env.BRANCH_NAME}", projectId: env.PROJECT, clusterName: env.CLUSTER, zone: env.CLUSTER_ZONE, manifestPattern: 'k8s/dev', credentialsId: env.JENKINS_CRED, verifyDeployments: true])
          echo 'To access your environment run `kubectl proxy`'
          echo "Then access your service via http://localhost:8001/api/v1/proxy/namespaces/${env.BRANCH_NAME}/services/${FE_SVC_NAME}:80/"
        }
      }
    }
  }
}
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ vi html.go
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ vi main.go
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git add Jenkinsfile html.go main.go
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git commit -m "Version 2.0.0"
[new-feature 19b700f] Version 2.0.0
 3 files changed, 4 insertions(+), 4 deletions(-)
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git push origin new-feature
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 2 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 487 bytes | 487.00 KiB/s, done.
Total 5 (delta 4), reused 0 (delta 0)
remote: Resolving deltas: 100% (4/4)
To https://source.developers.google.com/p/qwiklabs-gcp-03-919c526475cd/r/default
 * [new branch]      new-feature -> new-feature
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ kubectl proxy &
[2] 2136
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ Starting to serve on 127.0.0.1:8001

student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ curl \
> http://localhost:8001/api/v1/namespaces/new-feature/services/gceme-frontend:80/proxy/version
2.0.0
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git checkout -b canary
Switched to a new branch 'canary'
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git push origin canary
Total 0 (delta 0), reused 0 (delta 0)
To https://source.developers.google.com/p/qwiklabs-gcp-03-919c526475cd/r/default
 * [new branch]      canary -> canary
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ export FRONTEND_SERVICE_IP=$(kubectl get -o \
> jsonpath="{.status.loadBalancer.ingress[0].ip}" --namespace=production services gceme-frontend)
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ while true; do curl http://$FRONTEND_SERVICE_IP/version; sleep 1; done
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
1.0.0
^C
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git checkout master
Switched to branch 'master'
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git merge canary
Updating 73dcc86..19b700f
Fast-forward
 Jenkinsfile | 2 +-
 html.go     | 4 ++--
 main.go     | 2 +-
 3 files changed, 4 insertions(+), 4 deletions(-)
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ git push origin master
Total 0 (delta 0), reused 0 (delta 0)
To https://source.developers.google.com/p/qwiklabs-gcp-03-919c526475cd/r/default
   73dcc86..19b700f  master -> master
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ export FRONTEND_SERVICE_IP=$(kubectl get -o \
> jsonpath="{.status.loadBalancer.ingress[0].ip}" --namespace=production services gceme-frontend)
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$
student_03_cab8fcbc3799@cloudshell:~/continuous-deployment-on-kubernetes/sample-app (qwiklabs-gcp-03-919c526475cd)$ while true; do curl http://$FRONTEND_SERVICE_IP/version; sleep 1; done
1.0.0
1.0.0
1.0.0
...

2.0.0
2.0.0
2.0.0
2.0.0
2.0.0
2.0.0
```

Deploy to Kubernetes in Google Cloud: Challenge Lab
This challenge lab tests your skills and knowledge from the labs in the Kubernetes in Google Cloud quest. You should be familiar with the content of the labs before attempting this lab.

