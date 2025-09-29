@startuml
actor "Application / Workload" as App
actor "Vault Agent" as Agent
actor "Vault Venafi PKI Engine" as Vault
actor "Venafi TPP" as TPP

App --> (Use Injected Certificate)

Agent --> (Inject Certificate into Workload)
Agent --> Vault : Fetch certs/keys

Vault --> (Store Certificate & Metadata)
Vault --> (Renew Certificate)
Vault --> (Handle Expiry)
Vault --> (Revoke Certificate)
Vault --> TPP : Request / Manage certs

TPP --> (Generate Certificate & Key Pair)
TPP --> (Enforce Expiry)
TPP --> (Revoke Certificate in CRL/OCSP)

@enduml
