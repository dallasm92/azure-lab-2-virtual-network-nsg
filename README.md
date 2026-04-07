# Azure Lab 2: Virtual Network, Subnets, and NSG

## Objective

Build a basic Azure network foundation by creating a resource group, deploying a virtual network with separate public and private subnets, creating a network security group (NSG), adding custom inbound SSH rules, and associating the NSG only with the public subnet.

## Environment

- Platform: Microsoft Azure
- Subscription shown in evidence: `Azure subscription 1`
- Region: `East US`
- Evidence source: screenshots captured in the Azure portal

## Azure Services Used

- Resource Groups
- Virtual Networks
- Subnets
- Network Security Groups

## Resource Details

- Resource group: `rg-azure-lab-network`
- Virtual network: `vnet-lab-network`
- Address space: `10.20.0.0/16`
- Public subnet: `public-subnet` with `10.20.1.0/24`
- Private subnet: `private-subnet` with `10.20.2.0/24`
- Network security group: `nsg-lab-network`
- Custom inbound rule 1: `Allow-SSH-MyIP`, priority `1000`
- Custom inbound rule 2: `Deny-SSH-Internet`, priority `1010`

## Network Design

- The VNet uses a single address space: `10.20.0.0/16`.
- The public subnet is segmented as `10.20.1.0/24`.
- The private subnet is segmented as `10.20.2.0/24`.
- The NSG was associated only with `public-subnet`.
- `private-subnet` was intentionally left separate by design instead of being attached to the NSG shown in this lab.

## Steps Performed

1. Created the resource group `rg-azure-lab-network`.
2. Reviewed the resource group configuration and confirmed the deployment region.
3. Opened the resource group overview after creation.
4. Opened the Azure virtual networks landing page.
5. Started a new VNet deployment for `vnet-lab-network`.
6. Edited the original subnet entry into `public-subnet` with `10.20.1.0/24`.
7. Added `private-subnet` with `10.20.2.0/24`.
8. Confirmed both subnets on the IP addresses page.
9. Reviewed the VNet configuration before creation.
10. Completed the VNet deployment.
11. Opened the network security groups landing page.
12. Created `nsg-lab-network`.
13. Reviewed the NSG configuration before creation.
14. Completed the NSG deployment.
15. Confirmed the NSG inbound rules started with only the default rules.
16. Added `Allow-SSH-MyIP` to allow TCP/22 from the lab's current public IP.
17. Added `Deny-SSH-Internet` to deny TCP/22 from any other source.
18. Confirmed both custom inbound rules were present and ordered correctly.
19. Opened the NSG subnet association page.
20. Associated the NSG with `public-subnet`.
21. Verified the final VNet overview.
22. Verified the final VNet subnets view.
23. Verified the final NSG overview and inbound rule state.
24. Verified the final NSG subnets view.

## Screenshots

Use the files in [images](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images) as the evidence set for this lab.

1. [01-resource-group-create-page.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/01-resource-group-create-page.png)  
   Resource group creation form with `rg-azure-lab-network` and `East US`.
2. [02-resource-group-review-create.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/02-resource-group-review-create.png)  
   Review and create page for the new resource group.
3. [03-resource-group-overview.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/03-resource-group-overview.png)  
   Resource group overview after creation.
4. [04-virtual-networks-landing.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/04-virtual-networks-landing.png)  
   Azure virtual networks landing page before the VNet exists.
5. [05-virtual-network-basics.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/05-virtual-network-basics.png)  
   Create virtual network basics page for `vnet-lab-network`.
6. [06-edit-public-subnet.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/06-edit-public-subnet.png)  
   Public subnet edited to `10.20.1.0/24`.
7. [07-add-private-subnet.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/07-add-private-subnet.png)  
   Private subnet added as `10.20.2.0/24`.
8. [08-ip-addresses-both-subnets.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/08-ip-addresses-both-subnets.png)  
   IP addresses page showing both subnets in the VNet.
9. [09-vnet-review-create.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/09-vnet-review-create.png)  
   Review and create page for the VNet.
10. [10-vnet-deployment-complete.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/10-vnet-deployment-complete.png)  
    VNet deployment completed successfully.
11. [11-nsg-landing-page.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/11-nsg-landing-page.png)  
    Azure NSG landing page before the NSG exists.
12. [12-nsg-basics-page.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/12-nsg-basics-page.png)  
    NSG basics page for `nsg-lab-network`.
13. [13-nsg-review-create.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/13-nsg-review-create.png)  
    Review and create page for the NSG.
14. [14-nsg-deployment-complete.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/14-nsg-deployment-complete.png)  
    NSG deployment completed successfully.
15. [15-inbound-rules-before-custom.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/15-inbound-rules-before-custom.png)  
    Inbound security rules page before custom SSH rules were added.
16. [16-add-allow-ssh-myip-sensitive.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/16-add-allow-ssh-myip-sensitive.png)  
    Allow rule for SSH from the current public IP. The repository copy is redacted in place for public-safe publishing.
17. [17-add-deny-ssh-internet-sensitive.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/17-add-deny-ssh-internet-sensitive.png)  
    Deny rule for SSH from any other source. The repository copy is redacted in place for public-safe publishing.
18. [18-inbound-rules-with-custom-rules-sensitive.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/18-inbound-rules-with-custom-rules-sensitive.png)  
    Inbound rules list showing both custom rules. The repository copy is redacted in place for public-safe publishing.
19. [19-nsg-subnet-association-page.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/19-nsg-subnet-association-page.png)  
    NSG subnet association page with `public-subnet` selected.
20. [20-nsg-attached-to-public-subnet.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/20-nsg-attached-to-public-subnet.png)  
    NSG successfully associated to `public-subnet`.
21. [21-final-vnet-overview.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/21-final-vnet-overview.png)  
    Final VNet overview showing the address space and subnet count.
22. [22-final-vnet-subnets-page.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/22-final-vnet-subnets-page.png)  
    Final VNet subnets page showing both `public-subnet` and `private-subnet`.
23. [23-final-nsg-overview-sensitive.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/23-final-nsg-overview-sensitive.png)  
    Final NSG overview showing custom inbound rules and subnet association. The repository copy is redacted in place for public-safe publishing.
24. [24-final-nsg-subnets-page.png](/home/dallas/projects/azure-lab-2-virtual-network-nsg/images/24-final-nsg-subnets-page.png)  
    Final NSG subnets page showing only `public-subnet` attached.

## What I Learned

- A single VNet can be segmented cleanly into separate public and private subnets with non-overlapping CIDR ranges.
- NSG rule priority matters. The allow rule for my specific IP had to be higher priority than the broader deny rule.
- Associating an NSG at the subnet level lets me scope access controls to one subnet without automatically applying them to the other.
- Leaving `private-subnet` separate by design makes the network intent clearer for later labs that may need different controls.

## Problems Encountered / Notes

- Several screenshots expose the real public IP used in the SSH allow rule. Those images should be redacted before public portfolio publishing.
- The repository copies of the public-IP screenshots were redacted in place before publishing.
- The NSG was associated only with `public-subnet`.
- `private-subnet` was left unassociated to this NSG by design, which is visible in the final NSG subnets page showing only one attached subnet.
- `TODO`: If you want to claim end-to-end validation with deployed workloads later, add a follow-up lab that places test resources into each subnet.

## Cost Control and Cleanup

- This lab stayed focused on networking configuration rather than deployed compute resources.
- No NAT gateway, Azure Firewall, or Bastion deployment is shown in the evidence set.
- Keeping the lab at the resource-definition level is a good way to practice networking basics while minimizing cost exposure.
- `TODO`: Confirm whether `rg-azure-lab-network` was deleted after the lab if you want the repo to claim full cleanup completion.

## Outcome

The lab produced a working Azure network foundation with one VNet, two subnets, and a subnet-level NSG design. The final state shows `public-subnet` protected by custom SSH access rules while `private-subnet` remains separate for a more restricted follow-up design.
