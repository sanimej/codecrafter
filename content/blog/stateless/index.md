+++
layout="post"
title="Stateless firewall"
summary="When does it make sense to use a Stateless firewall"
date=2020-11-30
draft=false
[extra]
tags="iptables, firewall, netfilter,"
+++

## Statefull vs Stateless firewall

A statefull firewall maintains the state of connections it has seen. The implication of this is an explicit rule has to be created only for the first packet in the flow. The return packet can be allowed based on the state maintained.

<figure style="width:75%;margin:auto;">
    {{ resize_image(path="statefull.gif") }}
<figcaption style="text-align:center;">Fig 1: Network Architecture</figcaption>
<br/>
</figure>

In Linux firewall iptables can be configured to be statefull or stateless

<!-- more -->

## When is a stateless firewall useful

The most obvious case is when there is too much state to maintain because every state maintained costs a finite amount of resource.
A good scenario is the case of extremely busy servers, like a DNS server for example.
