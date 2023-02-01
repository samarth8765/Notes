## Need of kubernetes:
- Earlier we use monolithic architecture.But this architecture had many problems (you can read problems in Microservices.md).
- The above problem is solved by Microservices(lossely coupled).

- Open source container management tool which automates container deployment, container scaling and load balancing.
- It schedules, run, and manages isolated containers which are running on virtual/physical machines.
- Google initially developed this tool and later acquired by CNCF.
- It is written in GO language.

## Problem with scaling up the containers:
- Containers cannot communicate with each other.
- Autoscaling and load balancing is not possible.

## Features of kubernetes:
- Orchestration(clustering of any number of containers running on different networks).
- Autoscaling (vertical as well as horizontal)
- Autohealing
- Load Balancing
- Platform independent
- Fault tolerance
- Rollback (going back to previous version)
- Health monitoring
- Batch execution

- Kubernetes support two types of scripting langauges JSON and YAML.
- It works on Master-Slave archritecture.
- Each worker node contains multiple pods(smallest unit of kubernetes) and each pod can contain single or multiple containers.
- Kubernetes do not directly works with container rather they work with pods.