
- data node stores the actual data
- name node stores the metadata, it stores information about the where the chunk of file is to be read from
- Decrease the block size increases scope of parallel processing but the downside is the name node now need to store more meta data.
- Increasing the block size decrease the scope of parallel processing
- Admins can change block size according to the use case.
- We can add more data node if the data size increases.
- In newer version of Hadoop a concept of name node federation where we can split the meta data across multiple name nodes for scalability of name nodes.
- Replication factor is used to replicate the block is n nodes example replication factor is 3 then a block is stored in 3 nodes.
- Secondary name node is used for fault tolerance.
- name node federation is for scalability
- Rack is a set of node that kept in single geographical location
- Admins should not store the all three copies in on single rack.

## How the files are read?
![[hadoop_read_cycle.svg]]

## Hadoop Commands

It is similar to [[Linux commands]]