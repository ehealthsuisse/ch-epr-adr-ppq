# 3. Use Cases for Policy Set Templates

## 3.1. General remarks

1. During the onboarding of a patient, only the Policy Administrator can submit policy sets related to this patient.
After the onboarding, policy sets related to the patient can be submitted by the patient himself, 
by his representatives (if any), or by the Policy Administrator on behalf of the patient.  <br/><br/>
2. In the use case descriptions below, the statements "the patient wants", "the patient decides", etc. cover 
also situations when a representative (authorized by the means of a corresponding policy set) 
decides and acts on behalf of the patient.   <br/><br/>
3. A policy set can be updated either by an in-place modification (CH:PPQ-1 UpdatePolicy), or by
a deletion (CH:PPQ-1 DeletePolicy) followed by a resubmission (CH:PPQ-1 AddPolicy) of the policy set.
When modifying a policy set in-place, its ID and the EPR-SPID shall be not changed.    <br/><br/>
Healthcare professionals with the right to delegate permissions can perform only in-place modifications
of policy sets.   <br/><br/>
In regard to policy sets based on templates 301–304, and only when the patient 
(for policy sets based on template 301 — also a healthcare professional with the right to delegate permissions) 
wants to _broaden_ the permissions of a healthcare professional, a group of healthcare professionals, 
or a representative, i.e. to raise the confidentiality level of available documents or to extend the validity period,
the original policy set may be left untouched, and a new, additional policy set of the same type may be submitted.
The same is true for the prolongation of exclusion list memberships (a special flavor of policy sets based on template 301).   <br/><br/>
But it is nevertheless advisable to have at most one policy set for any given combination of template ID, EPR-SPID, 
and GLN/group OID/representative ID.   <br/><br/>
4. Putting a healthcare professional into the exclusion list (by submitting a corresponding policy set) 
will outpower all other policy sets applicable onto him.

## 3.2. Use Cases

**UC201-1: The patient gets the full access to his EPR**

This is a required step.  During the onboarding of the patient, the Policy Administrator shall submit 
a singleton policy set based on the template 201.  This policy set shall be neither modified nor 
deleted afterward.

Attributes to fill in the template:
- Policy set ID
- EPR-SPID


**UC202-1: The patient wants that documents from his EPR with particular confidentiality level(s) 
are available to any healthcare professional in case of emergency**

A singleton policy set based on the template 202 shall be submitted — either during the onboarding 
of the patient or later.  

Attributes to fill in the template:
- Policy set ID
- EPR-SPID
- Reference to a policy set corresponding to the chosen confidentiality level(s) of the documents 
  that shall be available to healthcare professionals in case of emergency


**UC202-2: The patient wants to reconfigure, documents of which confidentiality level(s) 
from his EPR shall be available to any healthcare professional in case of emergency**

The singleton policy set based on the template 202 shall be updated.


**UC202-3: The patient wants to disable access to documents in his EPR to healthcare professionals 
in case of emergency**

The singleton policy set based on the template 202 shall be deleted. 

Note: This will not affect permissions of healthcare professionals defined in policy sets based 
on templates 301, 302, and 304.


**UC203-1: The patient defines the lowest allowed confidentiality level of documents being submitted into his EPR** 

This is a required step.  During the onboarding of the patient, the Policy Administrator shall submit
a singleton policy set based on the template 203.  This policy set shall be not deleted afterward.

Attributes to fill in the template:
- Policy set ID
- EPR-SPID
- Reference to a policy set corresponding to the chosen lowest confidentiality level of documents
  being submitted into the patient's EPR


**UC203-2: The patient wants to reconfigure the lowest allowed confidentiality level of documents being submitted into his EPR**

The singleton policy set based on the template 203 shall be updated.


**UC301-1: The patient wants to give a particular healthcare professional a permission to read documents 
with particular confidentiality level(s)**

A policy set based on template 301 shall be submitted after the onboarding of the patient.

Attributes to fill in the template:
- Policy set ID
- EPR-SPID
- GLN of the healthcare professional
- Reference to a policy set corresponding to the chosen confidentiality level of documents
  that shall be available to this healthcare professional
- Optionally, start and end date of the validity


**UC301-2: The patient wants to change read permissions of a particular healthcare professional**

Policy set(s) based on template 301 and referencing this healthcare professional shall be updated.


**UC301-3: The patient wants to withdraw read permissions of a particular healthcare professional**

Policy set(s) based on template 301 and referencing this healthcare professional shall be deleted.


**UC301-4: The patient wants to prohibit any access to his EPR by a particular healthcare professional**

A policy set based on template 301 shall be submitted after the onboarding of the patient.

Attributes to fill in the template:
- Policy set ID
- EPR-SPID
- GLN of the healthcare professional
- Reference to the policy set corresponding to the "Exclusion List"
- Optionally, start and end date of the validity


**UC301-5: A healthcare professional "A" with delegation rights wants to delegate his read permissions
to another healthcare professional "B"**

A policy set based on template 301 shall be submitted _to the Policy Repository of the community
where the patient is onboarded_.

Attributes to fill in the template:
- Policy set ID
- EPR-SPID
- GLN of the healthcare professional "B"
- Reference to a policy set corresponding to the read permissions of the healthcare professional "A"
  (or lower), without delegation rights
- End date and optionally start date of the validity


**UC301-6: A healthcare professional "A" with delegation rights wants to change read permissions 
he delegated to another healthcare professional "B"**

Policy set(s) based on template 301 and referencing the healthcare professional "B" 
shall be modified in-place.


**UC301-7: A healthcare professional "A" with delegation rights wants to withdraw read permissions
he delegated to another healthcare professional "B"**

The healthcare professional "A" cannot perform this operation by himself.  Instead, he shall
contact the patient or the Policy Administrator of the community where the patient is onboarded.


**UC302-1: The patient wants to give a particular group of healthcare professionals 
a permission to read documents with particular confidentiality level(s)**

A policy set based on template 302 shall be submitted after the onboarding of the patient.

Attributes to fill in the template:
- Policy set ID
- EPR-SPID
- OID of the group of healthcare professionals
- Reference to a policy set corresponding to the chosen confidentiality level of documents
  that shall be available to this healthcare professional
- End date and optionally start date of the validity


**UC302-2: The patient wants to change read permissions of a particular group of healthcare professionals**

Policy set(s) based on template 302 and referencing this group of healthcare professionals shall be updated.


**UC302-3: The patient wants to withdraw read permissions of a particular group of healthcare professionals**

Policy set(s) based on template 302 and referencing this group of healthcare professionals shall be deleted.


**UC303-1: The patient wants to authorize a representative to manage the patient's EPR**

A policy set based on template 303 shall be submitted after the onboarding of the patient.

Attributes to fill in the template:
- Policy set ID
- EPR-SPID
- ID of the representative
- Optionally, start and end date of the validity


**UC303-2: The patient wants to change the validity period of a representative's permissions**

Policy set(s) based on template 303 and referencing this representative shall be updated.


**UC303-3: The patient wants to withdraw permissions of a representative**

Policy set(s) based on template 303 and referencing this representative shall be deleted.


**UC304-1: The patient wants to give a particular healthcare professional a permission to read documents
with particular confidentiality level(s) and to delegate this permission to other healthcare professionals**

A policy set based on template 304 shall be submitted after the onboarding of the patient.
Note that a policy set based on template 304 grants the delegation right only — an additional policy set
based on template 301, granting the healthcare professional's own access rights, is always required.

Attributes to fill in the template:
- Policy set ID
- EPR-SPID
- GLN of the healthcare professional
- Reference to a policy set corresponding to the chosen confidentiality level of documents
  that shall be available to this healthcare professional and delegable by him 
- End date and optionally start date of the validity


**UC304-2: The patient wants to change read and delegation permissions of a particular healthcare professional**

Policy set(s) based on template 304 and referencing this healthcare professional shall be updated.


**UC304-3: The patient wants to withdraw read and delegation permissions of a particular healthcare professional**

Policy set(s) based on template 304 and referencing this healthcare professional shall be deleted.


