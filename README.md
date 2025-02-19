**CS425 Project** 

| Akhil Sundaram  | Anurag Choudhary  |
| ------ | ------ |


**Distributed Group Membership and Failure Detection**


Created a group membership system which detects failures and maintains a real-time updated membership list at every node using the SWIMs algorithm. This implementation closely follows the same, with a few differences and modifications. 


**Project Structure**


>**Buffer** :
> This contains the buffer logic that will be piggybacked on every ping and pin-ack message.


>**Introducer** : 
> This contains the code for the "introducer" node, and this can be any VM (as long as the configuration inside introducer.go is set accordingly).


>**Membership** : 
> This contains code to maintain , update and modify the membership list at every node. It also contains the suspicion logic for enabling PingAck-Sus mechanism.


>**Ping** :
>This contains code to ping all the nodes in the system in a randomized manner from every other node. Integrates all the other mechanisms we have specified.


>**Utility** :
>This contains some utility methods that are used across all files.


**Code Instructions**


- **Start the Introducer**: Whichever machine is chosen to be the introducer, perform following on that node (by default, VM Node 1)


>`>$ cd MP2/`
>
>`>$ go run .`


**Start the other Nodes to join the system**: Run the same command on other nodes, and use the cli prompts to see the membership list at any node, at any time !


>`>$ cd MP2/`
>
>`>$ go run .`



**Enabling PingAck-Sus**: To enable the PingAck-Sus mechanism, we make use of MP1 code to distribute and signal all the machines to set Suspicion to True. 


> `>$ cd MP1/`
> `>$ cd Parser`
>
>`>$ go run . -cmd "sus" -o "" -s "test"`



>**PS** : This will toggle the suspicion flag, running this again will disable the Suspicion mechanism.


>**PS** : Before running this, ensure that Listeners are up in all the machines ! 

