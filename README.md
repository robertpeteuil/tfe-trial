# Demonstration Terraform Enterprise Sentinel Policies

Sample Sentinel Policies for Terraform Enterprise

---

These policies are defined as [Policy Sets](https://www.terraform.io/docs/enterprise/sentinel/manage-policies.html) using Terraform Enterprise VCS intergration.

## Introduction to HashiCorp Sentinel

- Introduction to Policy as Code and [Sentinel](https://docs.hashicorp.com/sentinel/concepts/policy-as-code)
- Writing [Sentinel Policies](https://docs.hashicorp.com/sentinel/writing/)
- Using the [Sentinel Simulator](https://docs.hashicorp.com/sentinel/commands/)

## Using Sentinel with Terraform Enterprise

- Using [Sentinel Policies with Terraform Enterprise](https://www.terraform.io/docs/enterprise/sentinel/index.html).
- Sample Terraform Sentinel policies and documentation located in [governance directory in terraform-guides](https://github.com/hashicorp/terraform-guides/tree/master/governance/second-generation).

## Note about Using with Private Terraform Enterprise

A portion of these policies test if resources are being destroyed using a new [destroy](https://www.terraform.io/docs/cloud/sentinel/import/tfplan.html#value-destroy) value that is present in Terraform Cloud (https://app.terraform.io), but not yet available in Private Terraform Enterprise (PTFE); expected October, 2019.

In order for these policies to work with PTFE, the following portions of the policies have been commented out:

``` ruby
if r.destroy {
  print("Skipping resource", address, "that is being destroyed.")
  continue
}
```

A more detailed explanation can be found in the [Terraform Guides repo](https://github.com/hashicorp/terraform-guides/tree/master/governance/second-generation#note-about-using-with-private-terraform-enterprise-ptfe)
