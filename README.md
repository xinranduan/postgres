# postgreSQL
This is collection of modified source code for postgreSQL that:
* uses [Most Recently Used (MRU)](https://en.wikipedia.org/wiki/Cache_replacement_policies#Most_Recently_Used_.28MRU.29) as databse buffer replacement policy,
* has an overridden OFFSET clause that skips every other k rows, 
* forces query optimizer to use nested loop join (except for FULL JOIN).

## MRU
Modified files:
* src/include/storage/buf_internals.h
* src/backend/storage/buffer/buf_init.c
* src/backend/storage/buffer/freelist.c
* src/backend/storage/buffer/bufmgr.c

## OFFSET
Modified files:
* /backenexecutor/nodeLimit.c

## Forced Nested Loop Join
Modified files:
* /backend/optimizer/createplan.c
