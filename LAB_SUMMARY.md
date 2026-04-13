# Lab Summary

## Lab

Azure Lab 2: Virtual Network, Subnets, and NSG

## Goal

Build an Azure network foundation with segmented subnets and a subnet-level NSG that restricts SSH access to a known public IP.

## Skills Demonstrated

- Azure virtual network and subnet design
- CIDR-based address planning
- NSG creation and subnet-level association
- Ordered inbound rule management with explicit allow and deny behavior
- Public-safe documentation through screenshot redaction

## Final State

- `vnet-lab-network` created with address space `10.20.0.0/16`
- `public-subnet` configured as `10.20.1.0/24`
- `private-subnet` configured as `10.20.2.0/24`
- `nsg-lab-network` created and associated only with `public-subnet`
- SSH restricted by `Allow-SSH-MyIP` at priority `1000` and `Deny-SSH-Internet` at priority `1010`

## Portfolio Value

This lab shows deliberate network segmentation and access control rather than default portal behavior. It demonstrates how to separate public and private network intent and how to enforce targeted SSH access with NSG rule priority.
