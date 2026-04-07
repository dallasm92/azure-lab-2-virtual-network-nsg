# Lab Summary

- Built an Azure virtual network lab with `vnet-lab-network`, a `10.20.0.0/16` address space, and separate public/private subnets for cleaner network segmentation.
- Created and configured `nsg-lab-network` with ordered custom inbound SSH rules: `Allow-SSH-MyIP` at priority `1000` and `Deny-SSH-Internet` at priority `1010`.
- Applied the NSG only to `public-subnet`, leaving `private-subnet` separate by design to support a more restricted internal segment.
- Documented the full Azure portal workflow with screenshot evidence covering resource creation, subnet design, NSG rule configuration, and final validation views.
- Redacted the public-IP screenshots in place so the published repo is safer to share publicly.
