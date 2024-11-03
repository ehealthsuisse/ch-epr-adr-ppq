# 2. Overview and relations among EPR policies and policy sets

Relations among EPR base policies, base policy sets, policy set templates, and user-defined policy sets generated from
these templates can be represented graphically in the following way (IDs of base policies and base policy sets are given
in a shortened form, without the common prefix `urn:e-health-suisse:2015:policies:`):

![Relations among EPR base policies, base policy sets, policy set templates, and user-defined policy sets generated from
these templates](policies.png)

Detailed descriptions of the elements of the EPR Official Policy Stack will be provided in the subsequent
sections. Target constraints of policies and policy sets will be represented as lists of allowed
document confidentiality codes, purposes of use, and user roles.

The following notational conventions apply:

* Asterisk `*` means that the target constraints do not address the corresponding attribute, i.e. that there is no
  restriction of its values.
* If a policy set references multiple policies or policy sets simultaneously, their IDs are separated by commas.
* If a policy set references a single policy or policy set from a list of alternatives, their IDs are separated by "or".
* If the target constraints of a policy set vary depending on which policies or policy sets it references, the syntax
  "ID of the referenced policy or policy set 🡒 resulting value" is used, e.g. "102 🡒 `NORMAL`".

## 2.1. Base policies

**Base policy 01:**

- File name: 01-base-policy-read-normal.xml
- Policy ID: `urn:e-health-suisse:2015:policies:permit-reading-normal`
- Effect: Permit to enquire document metadata and content
- Allowed document confidentiality code(s): `NORMAL`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): All excluding `TCU` (note 1)

**Base policy 02:**

- File name: 02-base-policy-read-restricted.xml
- Policy ID: `urn:e-health-suisse:2015:policies:permit-reading-restricted`
- Effect: Permit to enquire document metadata and contents
- Allowed document confidentiality code(s): `RESTRICTED`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): All excluding `TCU` (note 1)

**Base policy 03:**

- File name: 03-base-policy-read-secret.xml
- Policy ID: `urn:e-health-suisse:2015:policies:permit-reading-secret`
- Effect: Permit to enquire document metadata and contents
- Allowed document confidentiality code(s): `SECRET`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): All excluding `TCU` (note 1)

**Base policy 04:**

- File name: 04-base-policy-write-normal.xml
- Policy ID: `urn:e-health-suisse:2015:policies:permit-writing-normal`
- Effect: Permit to submit documents
- Allowed document confidentiality code(s): `NORMAL`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy 05:**

- File name: 05-base-policy-write-restricted.xml
- Policy ID: `urn:e-health-suisse:2015:policies:permit-writing-restricted`
- Effect: Permit to submit documents
- Allowed document confidentiality code(s): `RESTRICTED`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy 06:**

- File name: 06-base-policy-write-secret.xml
- Policy ID: `urn:e-health-suisse:2015:policies:permit-writing-secret`
- Effect: Permit to submit documents
- Allowed document confidentiality code(s): `SECRET`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy 07:**

- File name: 07-base-policy-policy-full.xml
- Policy ID: `urn:e-health-suisse:2015:policies:full-policy-administration`
- Effect: Permit to manage privacy policies
- Allowed document confidentiality code(s): n/a
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy 08:**

- File name: 08-base-policy-deny-all.xml
- Policy ID: `urn:e-health-suisse:2015:policies:deny-all`
- Effect: Deny all operations
- Allowed document confidentiality code(s): n/a
- Allowed purpose(s) of use: n/a
- Allowed user role(s): n/a

**Base policy 09:**

- File name: 09-base-policy-read-patient-audit.xml
- Policy ID: `urn:e-health-suisse:2015:policies:permit-reading-patient-audit`
- Effect: Permit to enquire patient-related audit records
- Allowed document confidentiality code(s): n/a
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy 10:**

- File name: 10-base-policy-update-metadata-normal.xml
- Policy ID: `urn:e-health-suisse:2015:policies:update-metadata-normal`
- Effect: Permit to modify document metadata **(starting from Release 2025 — only using ITI-57)**
- Allowed document confidentiality code(s): `NORMAL`
- Allowed purpose(s) of use: `NORM`
- Allowed user role(s): All excluding `TCU` (note 1)

**Base policy 11:**

- File name: 11-base-policy-update-metadata-restricted.xml
- Policy ID: `urn:e-health-suisse:2015:policies:update-metadata-restricted`
- Effect: Permit to modify document metadata **(starting from Release 2025 — only using ITI-57)**
- Allowed document confidentiality code(s): `RESTRICTED`
- Allowed purpose(s) of use: `NORM`
- Allowed user role(s): All excluding `TCU` (note 1)

**Base policy 12:**

- File name: 12-base-policy-update-metadata-secret.xml
- Policy ID: `urn:e-health-suisse:2015:policies:update-metadata-secret`
- Effect: Permit to modify document metadata **(starting from Release 2025 — only using ITI-57)**
- Allowed document confidentiality code(s): `SECRET`
- Allowed purpose(s) of use: `NORM`
- Allowed user role(s): All excluding `TCU` (note 1)

**Base policy 13 (starting from Release 2025):**

- File name: 13-base-policy-restricted-update-metadata-normal.xml
- Policy ID: `urn:e-health-suisse:2015:policies:restricted-update-metadata-normal`
- Effect: Permit to modify document metadata using ITI-92
- Allowed document confidentiality code(s): `SECRET`
- Allowed purpose(s) of use: `NORM`
- Allowed user role(s): All excluding `TCU` (note 1)

**Base policy 14 (starting from Release 2025):**

- File name: 14-base-policy-restricted-update-metadata-restricted.xml
- Policy ID: `urn:e-health-suisse:2015:policies:restricted-update-metadata-restricted`
- Effect: Permit to modify document metadata using ITI-92
- Allowed document confidentiality code(s): `RESTRICTED`
- Allowed purpose(s) of use: `NORM`
- Allowed user role(s): All excluding `TCU` (note 1)

**Base policy 15 (starting from Release 2025):**

- File name: 13-base-policy-restricted-update-metadata-secret.xml
- Policy ID: `urn:e-health-suisse:2015:policies:restricted-update-metadata-secret`
- Effect: Permit to modify document metadata using ITI-92
- Allowed document confidentiality code(s): `SECRET`
- Allowed purpose(s) of use: `NORM`
- Allowed user role(s): All excluding `TCU` (note 1)

Notes:

1. TCU is excluded indirectly because users in this role cannot claim purpose of use NORM or EMER. This is an
   intentional side effect.

## 2.2. Base policy sets

**Base policy set 101:**

- File name: 101-base-policyset-access-normal.xml
- Policy ID: `urn:e-health-suisse:2015:policies:access-level:normal`
- Referenced policies / policy sets: 01, 10
- Effect of referenced policies / policy sets: Permit to enquire document metadata and contents, and to modify document
  metadata
- Locally defined additional effect: --
- Allowed document confidentiality code(s): `NORMAL`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): All excluding `TCU`

**Base policy set 102:**

- File name: 102-base-policyset-access-restricted.xml
- Policy ID: `urn:e-health-suisse:2015:policies:access-level:restricted`
- Referenced policies / policy sets: 01, 02, 10, 11
- Effect of referenced policies / policy sets: Permit to enquire document metadata and contents, and to modify document
  metadata
- Locally defined additional effect: --
- Allowed document confidentiality code(s): `NORMAL`, `RESTRICTED`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): All excluding `TCU`

**Base policy set 103:**

- File name: 103-base-policyset-access-normal-with-delegation.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:access-level:delegation-and-normal`
- Referenced policies / policy sets: 101
- Effect of referenced policies / policy sets: Permit to enquire document metadata and contents, to modify document
  metadata, and to delegate these permissions to other HCPs
- Locally defined additional effect: Permit to add and modify privacy
  policies granting the permissions defined in 101
- Allowed document confidentiality code(s): `NORMAL`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): All excluding `TCU`

**Base policy set 104:**

- File name: 104-base-policyset-access-restricted-with-delegation.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:access-level:delegation-up-to-restricted`
- Referenced policies / policy sets: 102
- Effect of referenced policies / policy sets: Permit to enquire document metadata and contents, to modify document
  metadata, and to delegate these permissions to other HCPs
- Locally defined additional effect: Permit to add and modify privacy
  policies granting the permissions defined in 102
- Allowed document confidentiality code(s): `NORMAL`, `RESTRICTED`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): All excluding `TCU`

**Base policy set 105:**

- File name: 105-base-policyset-access-level-full.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:access-level:full`
- Referenced policies / policy sets: 01, 02, 03, 04, 05, 06, 07, 09, 10, 11, 12
- Effect of referenced policies / policy sets: Permit to perform all operations on all types of content
- Locally defined additional effect: --
- Allowed document confidentiality code(s): `*`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy set 106:**

- File name: 106-base-policyset-exclusion-list.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:exclusion-list`
- Referenced policies / policy sets: 08
- Effect of referenced policies / policy sets: Deny all operations
- Locally defined additional effect: --
- Allowed document confidentiality code(s): n/a
- Allowed purpose(s) of use: n/a
- Allowed user role(s): n/a

**Base policy set 107:**

- File name: 107-base-policyset-provide-restricted.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:provide-level:restricted`
- Referenced policies / policy sets: 05
- Effect of referenced policies / policy sets: Permit to submit documents with the confidentiality code `RESTRICTED`
- Locally defined additional effect: --
- Allowed document confidentiality code(s): `RESTRICTED`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy set 108:**

- File name: 108-base-policyset-provide-normal.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:provide-level:normal`
- Referenced policies / policy sets: 04, 05
- Effect of referenced policies / policy sets: Permit to submit documents with the confidentiality codes `NORMAL`
  and `RESTRICTED`
- Locally defined additional effect: --
- Allowed document confidentiality code(s): `NORMAL`, `RESTRICTED`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy set 109:**

- File name: 109-base-policyset-provide-secret.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:provide-level:secret`
- Referenced policies / policy sets: 06
- Effect of referenced policies / policy sets: Permit to submit documents with the confidentiality code `SECRET`
- Locally defined additional effect: --
- Allowed document confidentiality code(s): `SECRET`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `*`

**Base policy set 110:**

- File name: 110-base-policyset-policy-admin.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:policy-bootstrap`
- Referenced policies / policy sets: 07
- Effect of referenced policies / policy sets: Permit all operations on privacy policies
- Locally defined additional effect: User role is restricted to `PADM`
- Allowed document confidentiality code(s): `*`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `PADM`

**Base policy set 111:**

- File name: 111-base-policyset-doc-admin.xml:
- Policy ID: `urn:e-health-suisse:2015:policies:doc-admin`
- Referenced policies / policy sets: 01, 02, 03, 04, 05, 06, 10, 11, 12
- Effect of referenced policies / policy sets: Permit to enquire document metadata and contents, and to modify document
  metadata
- Locally defined additional effect: User role is restricted to `DADM`
- Allowed document confidentiality code(s): `*`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `DADM`

## 2.3. Templates for patient bootstrap policy sets

**Policy set template 201:**

- File name: 201-patient-full-access.xml
- Referenced policy set(s): 105
- Effect: Permits the patient (note 2) to perform any operations on their EPR
- Allowed document confidentiality code(s): `*`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `PAT`
- Attributes to fill in:
    - Policy set ID
    - EPR-SPID in `SubjectMatch`
    - EPR-SPID in `ResourceMatch`

**Policy set template 202:**

- File name: 202-patient-access-level.xml
- Referenced policy set(s): 101 or 102
- Effect: Defines the highest confidentiality level of documents any healthcare professional (note 3) can enquire in
  emergency mode
- Allowed document confidentiality code(s):
    - 101 🡒 `NORMAL`
    - 102 🡒 `NORMAL`, `RESTRICTED`
- Allowed purpose(s) of use: `EMER`
- Allowed user role(s): `HCP`
- Attributes to fill in:
    - Policy set ID
    - EPR-SPID in `ResourceMatch`
    - ID of the referenced policy set

**Policy set template 203:**

- File name: 203-patient-provide-level.xml
- Referenced policy set(s): 107 or 108 or 109
- Effect: Defined the lowest confidentiality level of documents being uploaded by any healthcare professional (note 3)
- Allowed document confidentiality code(s):
    - 107 🡒 `RESTRICTED`
    - 108 🡒 `NORMAL`, `RESTRICTED`
    - 109 🡒 `SECRET`
- Allowed purpose(s) of use: `NORM`, `AUTO`, `DICOM_AUTO`
- Allowed user role(s): `HCP`
- Attributes to fill in:
    - Policy set ID
    - EPR-SPID in `ResourceMatch`
    - ID of the referenced policy set

Notes:

2. A patient is defined as a user with the identifier type `urn:e-health-suisse:2015:epr-spid` and the role `PAT`.
3. A healthcare professional is defined as a user with the identifier type `urn:gs1:gln` and the role `HCP` (optionally
   served by an assistant or a technical user).
4. A member of a group of healthcare professionals is defined as a user with the identifier
   type `urn:oasis:names:tc:xspa:1.0:subject:organization-id` and the role `HCP`.

## 2.4. Templates for patient user assignment policy sets

**Policy set template ID 301:**

- File name: 301-patient-user-assignment-template.xml
- Referenced policy sets: 101 or 102 or 106
- Effect:
    - 101, 102 🡒 Permit a healthcare professional (note 3) identified by the given GLN to enquire metadata and
      content of documents with the given confidentiality code(s).
    - 106 🡒 Deny healthcare professional's access to the patient's EPR. This has a priority over all other policies and
      policy sets.
- Allowed document confidentiality code(s):
    - 101 🡒 `NORMAL`
    - 102 🡒 `NORMAL`, `RESTRICTED`
    - 106 🡒 n/a
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): `HCP`
- Time restriction: optional
- Attributes to fill in:
    - Policy set ID
    - GLN in `SubjectMatch`
    - EPR-SPID in `ResourceMatch`
    - Start date of the validity in `EnvironmentMatch` (optional if the end date is present, otherwise prohibited)
    - End date of the validity in `EnvironmentMatch` (optional)
    - ID of the referenced policy set

The element `Environments` shall be created only if the end date of the validity is provided.
Its sub-element `EnvironmentMatch` for the start date shall be created only if this date is provided.

**Policy set template ID 302:**

- File name: 302-patient-group-assignment-template.xml
- Referenced policy sets: 101 or 102
- Effect: Permit a group of healthcare professionals (note 4) identified by the given OID to enquire metadata and
  content of documents with the given confidentiality code(s).
- Allowed document confidentiality code(s):
    - 101 🡒 `NORMAL`
    - 102 🡒 `NORMAL`, `RESTRICTED`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): `HCP`
- Time restriction: required
- Attributes to fill in:
    - Policy set ID
    - Group OID in `SubjectMatch`
    - EPR-SPID in `ResourceMatch`
    - Start date of the validity in `EnvironmentMatch` (optional)
    - End date of the validity in `EnvironmentMatch`
    - ID of the referenced policy set

The element `EnvironmentMatch` for the start date shall be created only if this date is provided.

**Policy set template ID 303:**

- File name: 303-patient-representative-assignment-template.xml
- Referenced policy sets: 105
- Effect: Permit a representative (note 5) to perform any operations on the patient's EPR.
- Allowed document confidentiality code(s): `*`
- Allowed purpose(s) of use: `*`
- Allowed user role(s): `REP`
- Time restriction: optional
- Attributes to fill in:
    - Policy set ID
    - Representative ID in `SubjectMatch`
    - EPR-SPID in `ResourceMatch`
    - Start date of the validity in `EnvironmentMatch` (optional if the end date is present, otherwise prohibited)
    - End date of the validity in `EnvironmentMatch` (optional)
    - ID of the referenced policy set

The element `Environments` shall be created only if the end date of the validity is provided.
Its sub-element `EnvironmentMatch` for the start date shall be created only if this date is provided.

**Policy set template ID 304:**

- File name: 304-patient-user-assignment-with-delegation-template.xml
- Referenced policy sets: 103 or 104
- Effect: Same as respectively 101 or 102, but additionally permit to delegate the same permissions to other healthcare
  professionals during the permitted period of time.
- Allowed document confidentiality code(s):
    - 103 🡒 `NORMAL`
    - 104 🡒 `NORMAL`, `RESTRICTED`
- Allowed purpose(s) of use: `NORM`, `EMER`
- Allowed user role(s): `HCP`
- Time restriction: required
- Attributes to fill in:
    - Policy set ID
    - GLN in `SubjectMatch`
    - EPR-SPID in `ResourceMatch`
    - Start date of the validity in `ResourceMatch` (optional)
    - End date of the validity in `ResourceMatch`
    - Start date of the validity in `EnvironmentMatch` (optional)
    - End date of the validity in `EnvironmentMatch`
    - ID of the referenced policy set

Elements `ResourceMatch` and `EnvironmentMatch` for the start date shall be created only if this date is provided.
