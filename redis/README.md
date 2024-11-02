# ansible-redis
Initially created by David Wittman (https://github.com/DavidWittman/ansible-redis)
Altered for Bank of America use by Colin Cheline

## Contents

 1. [Getting Started](#getting-started)
 2. [Single Redis node](#single-redis-node)
 3. [Master-Slave Replication](#master-replica-replication)
 4. [Vault Integration](#vault-integration)
 5. [Custom Options](#custom-options)

## Getting started

This role expects to be run as a service account with become pbrun access (provided through ael/ataas_vars).

## Single Redis node
Create a group named "redis_master" with your redis node included.
Add your application servers to the "redis_sentinel" group.
Redis will be deployed to the single node with a cluster quorum of 1.

## Master-Slave replication
This allows you to have a single master and one or more read-only replica nodes.
Create a group named "redis_master" with a single redis master node included.
Create a group named "redis_replica" with your redis replica nodes included.
Add your application servers to the "redis_sentinel" group.
Redis will be deployed in a cluster configuration with quorum set to match the cluster sizing.

## Vault Integration

## Custom Options

