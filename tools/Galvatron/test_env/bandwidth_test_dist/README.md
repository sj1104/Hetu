# Communication Bandwidth Test
This directory contains scripts to test communication bandwidth on 16 GPUs for estimation of communication time in cost model.

## Main Idea

We test the communication coeffocient (comm_coe) between theoretical communication message size (MB) and real communication time (ms). Note that the communication bandwidth (MB/ms) is the reciprocal of comm_coe (ms/MB).

With the comm_coe, real communication time (ms) can be estimated by multiplying comm_coe to theoretical communication message size (MB):

$CommTimeEstimated(ms)=CommCoe(ms/MB)*MessageSize(MB)$

## Usage
1. Export the right ```MASTER_ADDR```, ```NCCL_SOCKET_IFNAME``` and ```NODE_RANK``` into environment for multi-node test.

2. Run ```sh test_allreduce_2nodes_all.sh``` to test the allreduce communication coefficient on 16 GPUs. 

3. Run ```sh test_p2p_2nodes_all.sh``` to test the P2P communication coefficient on 16 GPUs. 

Galvatron will automatically write the tested results into config files.