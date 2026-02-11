``` mermaid
flowchart TB

  %% ===== FRONTEND =====
  subgraph FE[React Frontend]
    FE1[UI Pages<br>Login<br>Listings<br>Create Listing<br>Messages<br>Profile]
    FE2[API Client<br>HTTP Requests]
    FE1 --> FE2
  end

  %% ===== BACKEND =====
  subgraph BE[Python Backend Monolith]
    BE0[REST API Layer]
    BE1[Auth and Email Verification]
    BE2[Listings Service]
    BE3[Messaging Service]
    BE4[Business Logic and Validation]
    BE5[Data Access Layer]

    BE0 --> BE4
    BE4 --> BE1
    BE4 --> BE2
    BE4 --> BE3
    BE1 --> BE5
    BE2 --> BE5
    BE3 --> BE5
  end

  %% ===== DATABASE =====
  subgraph DB[SQLite Database]
    T1[(Users)]
    T2[(VerificationCodes)]
    T3[(Listings)]
    T4[(ListingImages)]
    T5[(Messages)]
  end

  %% ===== DATA FLOW =====
  FE2 --> BE0
  BE5 --> T1
  BE5 --> T2
  BE5 --> T3
  BE5 --> T4
  BE5 --> T5

```
