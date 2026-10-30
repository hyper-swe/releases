# HyperSWE Beta Terms of Use

Last updated: October 30, 2026

## 1. Introduction

Welcome to HyperSWE. HyperSWE reviews the code changes your coding agents
make, maps your codebase, and places production tracebacks on that map. It
provides independent review, approval gates, and a receipt trail of what was
checked and approved.

These Beta Terms of Use ("Terms") are an agreement between you and
Astutic Artificial Intelligence Private Limited ("HyperSWE", "we", "us" or
"our"). They apply to the HyperSWE beta software, including the binaries we
publish, the install script, updates, and related documentation (together,
the "Software").

By downloading, installing or using the Software, you agree to these Terms.
If you use the Software on behalf of a company or other organization, you
confirm that you are authorized to accept these Terms for it, and "you"
includes that organization. If you do not agree to these Terms, do not
install or use the Software.

## 2. License to use the Software

Subject to these Terms, we grant you a free, personal, non-exclusive,
non-transferable, non-sublicensable and revocable license to install and use
the Software, in object-code form, for your own internal purposes, including
your commercial software development work.

The HyperSWE core is proprietary. We and our licensors keep all rights,
title and interest in the Software, including all intellectual property
rights. These Terms do not grant you any right to the source code of the
HyperSWE core, or to our names, logos or trademarks. All rights not expressly
granted in these Terms are reserved.

### Restrictions

Except as these Terms expressly allow, or as an open-source license that
applies to a component expressly allows (see section 3), you will not:

- sell, resell, rent, lease, sublicense or otherwise distribute the
  Software, or offer it to third parties as a hosted or managed service;
- reverse engineer, decompile or disassemble the Software, or try to derive
  its source code, except to the extent applicable law permits this despite
  this restriction;
- modify the Software or create derivative works of it;
- remove, alter or obscure any proprietary notice, license notice or
  attribution in the Software;
- bypass or disable any technical limitation or security feature of the
  Software; or
- use the Software in violation of applicable law, including export control
  and sanctions laws.

## 3. Open-source components

The Software includes components that are licensed under open-source
licenses. The installer also installs two companion tools, mgit and mtix,
which are licensed under the Apache License, Version 2.0. Some HyperSWE
modules, including the verifier and the plugin, are also licensed under the
Apache License, Version 2.0.

Each open-source component is governed by its own license, which you can
find in the component's repository or in the notices distributed with the
Software. If these Terms conflict with an open-source license for a
component, that license governs the component. Nothing in these Terms
limits any right you have under an open-source license.

## 4. Beta status

The Software is a beta release. We are actively developing it, so features,
commands, file formats and behavior may change, and we may add, change,
suspend or discontinue any part of the Software, or the beta program, at any
time. We may release updates that you need to install to keep using some
features.

The beta is free. We may introduce paid plans or fees in the future. If we
do, we will tell you before any fee applies to your use, and you can decide
whether to continue.

Beta software may contain defects and is not intended to be the sole
safeguard for your systems. We welcome your reports of problems; see
section 7.

## 5. Your code and your content

HyperSWE runs on your machine. It does not upload your source code to us.

You keep all rights to your source code, data and other content that you
use with the Software ("Your Content"), and to the reviews, maps, receipts,
reports and other output the Software produces for you ("Output"). We do
not claim ownership of Your Content or Output. Output is generated with the
help of automated systems and may be incomplete or inaccurate. You decide
how to use it.

You are responsible for Your Content, for having the rights you need to use
it with the Software, and for the agents, accounts, permissions and
credentials you configure the Software to use.

## 6. Third-party services

You can choose to connect the Software to services that third parties
provide, such as model providers, coding agents and git hosting services
("Third-Party Services"). When you do, the Software sends data to those
services at your direction, using the credentials you supply.

Your use of a Third-Party Service is governed by your agreement with its
provider, including its terms, privacy practices and pricing. You are
responsible for any usage charges, fees or quotas incurred with those
providers, including charges caused by actions the Software takes on your
behalf. We do not control Third-Party Services and are not responsible for
them, and their availability is not guaranteed.

## 7. Feedback

You can send us feedback, such as bug reports, suggestions and feature
requests, through the Software or by other means. Sending feedback is
optional. Before a feedback submission is shown for approval, the Software
removes code, credentials and other secrets, email addresses, user names,
host names, IP addresses, file paths, and repository and company names. A
submission contains only its text, its kind (friction, bug or idea), the
command it relates to, the Software version and your operating system.
Nothing is sent unless the submission is approved, by you or by an approver
you name. Approved submissions may be held on your machine and sent later.

If you send us feedback, you grant us a worldwide, perpetual, irrevocable,
royalty-free license to use, copy, modify and incorporate it into our
products and services, without any obligation to you. Please do not include
confidential information, credentials or source code you do not want to
share in your feedback.

## 8. Usage analytics

This version of the Software does not collect or send usage analytics. If a
future version does, we will update these Terms before it does so, and that
version will tell you what it collects and how to turn it off.

## 9. Update check

The Software checks our public release feed at most once a day so that it
can tell you when a newer version is available. If a check does not
complete, the Software tries again after six hours.

Each check sends only the installed Software version, your operating system
and your processor architecture. Our release feed is hosted by GitHub,
which, like any service that receives a request over the internet, sees
your IP address. The update check never downloads or installs anything;
whether and when to upgrade is your choice.

You can turn the update check off at any time in any of these ways:

- set `HYPERSWE_UPDATE_CHECK=0` in your environment;
- set `DO_NOT_TRACK=1` in your environment; or
- set `"enabled": false` in your `updatecheck.json` file.

The update check is separate from usage analytics.

## 10. Disclaimer of warranties

THE SOFTWARE AND ALL OUTPUT ARE PROVIDED "AS IS" AND "AS AVAILABLE", WITH
ALL FAULTS AND WITHOUT WARRANTY OF ANY KIND. TO THE MAXIMUM EXTENT
PERMITTED BY APPLICABLE LAW, HYPERSWE AND ITS AFFILIATES, LICENSORS AND
SUPPLIERS DISCLAIM ALL WARRANTIES AND CONDITIONS, WHETHER EXPRESS, IMPLIED
OR STATUTORY, INCLUDING ANY WARRANTIES OR CONDITIONS OF MERCHANTABILITY,
SATISFACTORY QUALITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE, QUIET
ENJOYMENT, ACCURACY AND NON-INFRINGEMENT, AND ANY WARRANTIES ARISING FROM
COURSE OF DEALING OR USAGE OF TRADE.

WITHOUT LIMITING THE ABOVE, WE DO NOT WARRANT THAT THE SOFTWARE WILL BE
UNINTERRUPTED, SECURE OR ERROR-FREE, THAT IT WILL DETECT EVERY DEFECT,
VULNERABILITY OR UNSAFE CHANGE, THAT ANY OUTPUT WILL BE ACCURATE OR
COMPLETE, OR THAT ANY THIRD-PARTY SERVICE WILL BE AVAILABLE OR WORK WITH
THE SOFTWARE. YOU ARE RESPONSIBLE FOR DECIDING WHETHER THE SOFTWARE AND ITS
OUTPUT ARE SUITABLE FOR YOUR PURPOSES.

## 11. Limitation of liability

TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, IN NO EVENT WILL
HYPERSWE OR ITS AFFILIATES, LICENSORS OR SUPPLIERS BE LIABLE FOR ANY
INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, EXEMPLARY OR PUNITIVE DAMAGES,
OR FOR ANY LOSS OF PROFITS, REVENUE, BUSINESS, GOODWILL OR ANTICIPATED
SAVINGS; LOSS OR CORRUPTION OF DATA OR CODE; WORK STOPPAGE; COMPUTER
FAILURE OR MALFUNCTION; COST OF SUBSTITUTE GOODS OR SERVICES; OR CHARGES,
FEES OR COSTS INCURRED WITH THIRD-PARTY SERVICES, ARISING OUT OF OR RELATED
TO THESE TERMS, THE SOFTWARE OR ANY OUTPUT, OR YOUR USE OF OR INABILITY TO
USE THEM, HOWEVER CAUSED AND UNDER ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, TORT (INCLUDING NEGLIGENCE), STRICT LIABILITY OR OTHERWISE, EVEN
IF WE HAVE BEEN ADVISED OF THE POSSIBILITY OF THOSE DAMAGES.

TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, OUR TOTAL AGGREGATE
LIABILITY FOR ALL CLAIMS ARISING OUT OF OR RELATED TO THESE TERMS, THE
SOFTWARE OR ANY OUTPUT WILL NOT EXCEED THE GREATER OF (A) THE AMOUNTS YOU
PAID US FOR THE SOFTWARE IN THE 12 MONTHS BEFORE THE EVENT GIVING RISE TO
THE CLAIM, AND (B) US$100.

These limitations apply even if a remedy fails of its essential purpose.
They are an essential part of the bargain between you and us, and we would
not provide the Software free of charge without them.

### Rights that cannot be limited

Some jurisdictions do not allow the exclusion of certain warranties or the
limitation of certain liabilities. Nothing in these Terms excludes or limits
any liability that cannot be excluded or limited under applicable law,
including liability for death or personal injury caused by negligence, or
for fraud, gross negligence or willful misconduct where the law does not
permit that liability to be limited. If you are a consumer, you may have
statutory rights that these Terms do not affect.

## 12. Termination

These Terms apply from when you first install or use the Software until
they are terminated.

You can stop using the Software and uninstall it at any time. We may
suspend or terminate your license to use the Software at any time, for
example if you breach these Terms or if we end the beta program. When these
Terms end, your license to use the Software ends, and you must stop using
and uninstall the Software. Ending these Terms does not affect your rights
under any open-source license that applies to a component.

Sections 2 (the parts on ownership and restrictions), 5, 7, 10, 11, 13, 14
and 15 survive termination.

## 13. Changes to these Terms

We may update these Terms from time to time, for example to reflect changes
to the Software or to the law. We will post the updated Terms with a new
"Last updated" date and, for material changes, we will give reasonable
notice, such as in the release notes or in the Software. Changes apply from
the date they are posted, or from a later date we state. If you continue to
use the Software after a change takes effect, you accept the updated Terms.
If you do not agree, stop using the Software.

## 14. Governing law and disputes

These Terms are governed by the laws of India, without regard to its
conflict-of-laws rules. The courts located in Mumbai, India have exclusive
jurisdiction over any dispute arising out of or related to these Terms or
the Software, and you and we consent to that jurisdiction. This section does
not deprive you of any protection that you have under the mandatory laws of
the country where you live.

## 15. General

- **Entire agreement.** These Terms, together with the licenses for the
  open-source components, are the entire agreement between you and us about
  the Software, and replace any prior agreement on that subject.
- **Severability.** If any provision of these Terms is held unenforceable,
  it will be enforced to the maximum extent permitted, and the rest of these
  Terms remain in effect.
- **No waiver.** If we do not enforce a provision, that is not a waiver of
  our right to enforce it later.
- **Assignment.** You may not assign or transfer these Terms without our
  written consent. We may assign these Terms in connection with a change of
  control, acquisition, or sale of all or substantially all of our assets.
- **Independent parties.** These Terms do not create any partnership,
  agency or employment relationship.

## 16. Contact

If you have questions about these Terms or the Software, contact us at
swe@hyperswe.com.

Astutic Artificial Intelligence Private Limited
