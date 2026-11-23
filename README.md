# virtualisation_cloud_computing
Td 1 virtualisation cloud computing

On créer le providers : 

┌──(DanielKali㉿DANIELEU)-[~/virtualisation_cloud_computing]
└─$ cat providers.tf
provider "google" {
  project     = "polytech-dijon"
  region      = "europe-west1"
  access_token = "patate"

}
(DanielKali㉿DANIELEU)-[~/virtualisation_cloud_computing]
└─$ terraform plan
No changes. Your infrastructure matches the configuration.

Terraform has compared your real infrastructure against your configuration and found no differences, so no changes are
needed.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

┌──(DanielKali㉿DANIELEU)-[~/virtualisation_cloud_computing]
└─$ cat main.tf
resource "google_compute_network" "vpc_network" {
  name = "vpc-network"
}

┌──(DanielKali㉿DANIELEU)-[~/virtualisation_cloud_computing]
└─$ terraform plan

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the
following symbols:
  + create

Terraform will perform the following actions:

  # google_compute_network.vpc_network will be created
  + resource "google_compute_network" "vpc_network" {
      + auto_create_subnetworks                   = true
      + bgp_always_compare_med                    = (known after apply)
      + bgp_best_path_selection_mode              = (known after apply)
      + bgp_inter_region_cost                     = (known after apply)
      + delete_bgp_always_compare_med             = false
      + delete_default_routes_on_create           = false
      + deletion_policy                           = "DELETE"
      + gateway_ipv4                              = (known after apply)
      + id                                        = (known after apply)
      + internal_ipv6_range                       = (known after apply)
      + mtu                                       = (known after apply)
      + name                                      = "vpc-network"
      + network_firewall_policy_enforcement_order = "AFTER_CLASSIC_FIREWALL"
      + network_id                                = (known after apply)
      + numeric_id                                = (known after apply)
      + project                                   = "polytech-dijon"
      + routing_mode                              = (known after apply)
      + self_link                                 = (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.

───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if
you run "terraform apply" now.






