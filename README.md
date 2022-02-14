# -ELEC-E7910---Special-Project
The topic is related to ultra-reliable low latency communication based on grant free communication, i.e. random access. Some background can be found in the attached papers. 

The idea is to consider interference canceling codes with M-IC, as discussed in the Boyd-papers. Specifically, the idea is that there is a population of users. There is a kind of “access frame” of n access slots.  Each user has an access sequence, meaning that the user transmits the same data repeated in multiple access slots in the “access frame”. The access slots where the users transmit their messages, are arranged in such a way that always if there is at most M users, one may perform Serial Interference Cancelation (SIC) such that each of the accessing users has a interference free slot at some stage of the decoding. 

The most recent paper Boyd 2019 shows that one can create M-IC codes from combinatorial Steiner-designs. A Steiner system S(t,k,n) yields a \lceil k((t-1) \rceil -IC code. 

There is a simulation with Steiner system (3,5,26) where one can have up to 260 users, each having their own access sequence. The point here is that with this arrangement, one can guarantee very high probability of reception, despite randomness of access, see fig 2 in Boyd2019. Note that here there are 26 resources and 260 users, and one can guarantee that any combination of 3 simultaneous users can be decoded. As compared to orthogonal resource allocation, where one could guarantee that all users are always decoded, one has 10x more users with this principle. 

Now we could think about one direction where a simulation study of such a URLLC MAC scheme could be generalized.

If the slots are, at least partially in the time domain, the designs of the type discussed in the Boyd paper have a problem that the number of access opportunities gets reduced, as one has to combine many slots to an access frame, and the users are assumed to access in a access frame, not a slot. Now, there is a simple cure for this. Consider a user who has a specific access sequence, where a massage is repeated K times in the slots in a frame. Say that K=3 and N=10. The access sequence would be  0010100010. Now the user gets the need to access in the fourth slots. Then, the user transmits 0100010 in the end of the current access frame, and 001 in the beginning of the next. Now, of course if 0100010001 guarantees M-IC in an access slot, also 000 0100010 transmitted in the first slot, and 001 0000000 more than guarantees M-IC I both slots. The access intensity on the frame-level, is doubled, however. Aim is to compare this to the arrangement simulated in Boyd2019, where access happens only in an access frame. 
