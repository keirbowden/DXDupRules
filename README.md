# DXDupRules
Repository containing an example of the issue I'm seeing converting source with duplicate rules.

There is a single duplicate rule

Executing :

    sfdx force:mdapi:convert --rootdir FromOrg

converts this to a subdirectory:

    State  Full Name                  Type           Workspace Path
    ─────  ─────────────────────────  ─────────────      ──────────────────────────────────────────────────────────────────────────────────────
    Add    Account.Account_Duplicate  DuplicateRule  force-app/main/default/duplicateRules/Account/Account_Duplicate.duplicateRule-meta.xml

When I try to push this to a scratch org, I get a fatal error from the sfdx tool, but if I open Deployment Status in the org I can see a little more detail:

    Fatal Error
    null: Need to specify full name, Name:Account_Duplicate, Delimiter:.

