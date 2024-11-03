# Official EPR Policy Stack

*Author: [Dmytro Rud](mailto:dmytro.rud@gmail.com), last change: 03-Nov-2024.*

According to chapter 4 of amendment 2.1 of annex 5 [EPRO-FDHA](https://www.fedlex.admin.ch/eli/oc/2023/221/de/annexes),
the official EPR [policy stack](https://github.com/ehealthsuisse/ch-epr-adr-ppq/tree/main/Privacy%20Policy%20Stack)
consists from:

* base policies,
* base policy sets,
* templates for patient bootstrap policy sets,
* templates for patient user assignment policy sets.

Their format is the Extensible Access Control Markup Language ([XACML](https://www.oasis-open.org/standard/xacmlv2-0/))
version 2.0.

The given document aims at describing structures of EPR policies and policy sets (intentionally not as detailed as
in the official XACML specification referenced above), relationships among them, and the Schematron script used
for the validation of the policy sets generated from the templates mentioned in the two last bullet points.

Contents:
1. [Structures of policies and policy sets](1_Structures.md)
2. [Relations between elements of the official EPR policy stack](2_Relations.md)
3. [Which policy set template to use for which use case](3_UseCases.md)
4. [Schematron validation of policy set submissions](4_Schematron.md)
