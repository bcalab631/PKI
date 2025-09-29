@startuml
rectangle "Application / Workload" as App {
  [Uses Injected Certificate]
}

rectangle "Vault Agent" as Agent {
  [Fetch Certificate]
  [Inject Certificate]
}

rectangle "Vault Venafi PKI Engine" as Vault {
  [Request Certificate]
  [Store Metadata]
  [Renew Certificate]
  [Revoke Certificate]
}

rectangle "Venafi TPP" as TPP {
  [Generate Certificate & Key]
  [Enforce Expiry]
  [Publish Revocation (CRL/OCSP)]
}

App --> Agent : Needs cert
Agent --> Vault : Fetch/renew cert
Vault --> TPP : API calls for issuance/renewal/revocation
TPP --> Vault : Returns cert + status
Vault --> Agent : Provides cert
Agent --> App : Injects cert
@enduml
