---
id: "5d7bc1ff-3a3e-4b61-8117-f7878affe14e"
title: "Digital Archiving 3 Extractor Input and Output Structure"
slug: "digital-archiving-3-extractor-input-and-output-structure"
category: "Extract Documents (DA) Batch Workflow Task Reference"
category_path:
  - "Product guides"
  - "Batch Workflows"
  - "Batch Workflows Reference Guides"
  - "Doxee Platform Batch Workflows Task Reference"
  - "Extract Documents (DA) Batch Workflow Task Reference"
status: "published"
content_type: "block"
version: 1
public_version: 1
created_at: "2025-12-08T09:28:33.354Z"
modified_at: "2025-12-17T18:16:11.636Z"
authors:
  - name: "Migration Team"
    email: "d360migrationteam@kovai.co"
source_url: "https://docs.doxee.com/docs/en/digital-archiving-3-extractor-input-and-output-structure"
synced_at: "2026-01-28T20:49:10.651Z"
checksum: "deedd22f8518b3dc"
---

## Introduction
There are different modes to invoke the DA3 Extractor:

**Mode**

**Input**

**Output**

**Documents Only**

Search request XML file

Document files (for example: PDF)

**Metadata and Documents**

Search request XML file

Document metadata XML file + document files (for example: PDF)

**Metadata and Documents embedded**

Search request XML file

Document metadata XML file with documents embedded in Base64 encoding

**Metadata Only**

Search request XML file

Document metadata XML file

## Search request (input file) structure
The format of the search request is the same for all extraction modes. The search request includes the following configurable elements:

**Element**

**Examples**

**Mandatory**

**Count**

**Query element XPath**

//FILE/DOCUMENT/TEMPLATE/DA

//INVOICES/INVOICE/EXTRACT

X

1

**Document category attribute**

//FILE/DOCUMENT/TEMPLATE/DA

/@documentCategory

//INVOICES/INVOICE/EXTRACT/@class

1

**Query attributes**

//FILE/DOCUMENT/TEMPLATE/DA

/@INVOICE_NUMBER

//INVOICES/INVOICE/EXTRACT /@ISSUE_D ATE

//INVOICES/INVOICE/EXTRACT /@DOC_NU MBER

X

1...n

### Examples
**Query Element Path //FILE/DOCUMENT/TEMPLATE/DA**

`&lt;FILE&gt;
  &lt;DOCUMENT&gt;
    &lt;TEMPLATE&gt;
      &lt;DA INVOICE_NUMBER="AS001" documentCategory="Invoices" /&gt;
    &lt;/TEMPLATE&gt;
    &lt;TEMPLATE&gt;
      &lt;DA INVOICE_NUMBER="AS002" documentCategory="Invoices" /&gt;
    &lt;/TEMPLATE&gt;
  &lt;/DOCUMENT&gt;
  &lt;DOCUMENT&gt;
    &lt;TEMPLATE&gt;
      &lt;DA INVOICE_NUMBER="AS003" documentCategory="Invoices" /&gt;
    &lt;/TEMPLATE&gt;
  &lt;/DOCUMENT&gt;
&lt;/FILE&gt;`**Query Element Path //FILE/DOCUMENT/TEMPLATE/DA**

`&lt;FILE&gt;
  &lt;DOCUMENT&gt;
    &lt;TEMPLATE&gt;
      &lt;DA INVOICE_NUMBER="AS*" documentCategory="Invoices" /&gt;
    &lt;/TEMPLATE&gt;
  &lt;/DOCUMENT&gt;
&lt;/FILE&gt;`**Query Element Path //INVOICES/INVOICE/EXTRACT**

`&lt;INVOICES&gt;
  &lt;INVOICE&gt;
     &lt;EXTRACT DOC_NUMBER="AS001" ISSUE_DATE="2019-07-20" class="Invoices" /&gt;
  &lt;/INVOICE&gt;
  &lt;INVOICE&gt;
     &lt;EXTRACT DOC_NUMBER="AS002" ISSUE_DATE="2019-07-20" class="Invoices" /&gt;
  &lt;/INVOICE&gt;
&lt;/INVOICES&gt;`## Document metadata (output file) structure
The structure of metadata output file is the same as the search request enriched with some elements.

**Element**

**Examples**

**Description**

**Count**

**Metadata element**

//FILE/DOCUMENT/TEMPLATE/DA/metadata

//INVOICES/INVOICE/EXTRACT/metadata

Fixed element **&lt;metadata&gt; **descendant of the query element

> Note

One **&lt;metadata&gt; **element for each document found.

1

**Payload element**

//FILE/DOCUMENT/TEMPLATE/DA/payload

//INVOICES/INVOICE/EXTRACT/payload

Fixed element **&lt;payload&gt; **descendant of the query element.

1

**Metadata attributes**

//FILE/DOCUMENT/TEMPLATE/DA

/metadata@INVOICE_NUMBER

//INVOICES/INVOICE/EXTRACT/metadata/@ISSUE_DA TE

//INVOICES/INVOICE/EXTRACT/metadata/@DOC_NUM BER

All metadata configured for the specific document category

1...n

### Examples
**Only metadata**

`&lt;FILE&gt;
    &lt;DOCUMENT&gt;
        &lt;TEMPLATE&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="XXXXX"&gt;
                &lt;metadata ID="BP-107005-0000000001231198-1" firstName="XXXXX" lastName="XXXXX" version="1"/&gt;
                &lt;metadata ID="BP-107001-0000000001231198-2" firstName="XXXXX" lastName="XXXXX" version="2"/&gt;
                &lt;metadata ID="BP-107223-0000000001231198-3" firstName="XXXXX" lastName="XXXXX" version="3"/&gt;
            &lt;/DA&gt;
        &lt;/TEMPLATE&gt;
    &lt;/DOCUMENT&gt;
    &lt;DOCUMENT&gt;
        &lt;TEMPLATE&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="YYYYY"&gt;
                &lt;metadata ID="BP-107005-0000000001231198-4" firstName="YYYYY" lastName="YYYYY" version="1"/&gt;
                &lt;metadata ID="BP-107001-0000000001231198-5" firstName="YYYYY" lastName="YYYYY" version="2"/&gt;
                &lt;metadata ID="BP-107223-0000000001231198-6" firstName="YYYYY" lastName="YYYYY" version="3"/&gt;
            &lt;/DA&gt;
        &lt;/TEMPLATE&gt;
    &lt;/DOCUMENT&gt;
&lt;/FILE&gt;`**Only metadata (replicate query element)**

`&lt;FILE&gt;
    &lt;DOCUMENT&gt;
        &lt;TEMPLATE&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="XXXXX"&gt;
                &lt;metadata ID="BP-107005-0000000001231198-1" firstName="XXXXX" lastName="XXXXX" version="1"/&gt;
            &lt;/DA&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="XXXXX"&gt;
                &lt;metadata ID="BP-107001-0000000001231198-2" firstName="XXXXX" lastName="XXXXX" version="2"/&gt;
            &lt;/DA&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="XXXXX"&gt;
                &lt;metadata ID="BP-107223-0000000001231198-3" firstName="XXXXX" lastName="XXXXX" version="3"/&gt;
            &lt;/DA&gt;
        &lt;/TEMPLATE&gt;
    &lt;/DOCUMENT&gt;
    &lt;DOCUMENT&gt;
        &lt;TEMPLATE&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="YYYYY"&gt;
                &lt;metadata ID="BP-107005-0000000001231198-4" firstName="YYYYY" lastName="YYYYY" version="1"/&gt;
            &lt;/DA&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="YYYYY"&gt;
                 &lt;metadata ID="BP-107001-0000000001231198-5" firstName="YYYYY" lastName="YYYYY" version="2"/&gt;
            &lt;/DA&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="YYYYY"&gt;
               &lt;metadata ID="BP-107223-0000000001231198-6" firstName="YYYYY" lastName="YYYYY" version="3"/&gt;
            &lt;/DA&gt;
        &lt;/TEMPLATE&gt;
    &lt;/DOCUMENT&gt;
&lt;/FILE&gt;`**Metadata and documents**

`&lt;FILE&gt;
    &lt;DOCUMENT&gt;
        &lt;TEMPLATE&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="XXXXX" version="1"&gt;
                &lt;metadata ID="BP-107001-0000000001231198-6" firstName="XXXXX" lastName="XXXXX" version="1"/&gt;
            &lt;/DA&gt;
        &lt;/TEMPLATE&gt;
    &lt;/DOCUMENT&gt;
    &lt;DOCUMENT&gt;
        &lt;TEMPLATE&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="YYYYY" version="2"&gt;
                &lt;metadata ID="BP-107001-0000000001231198-5" firstName="YYYYY" lastName="YYYYY" version="2"/&gt;
            &lt;/DA&gt;
        &lt;/TEMPLATE&gt;
    &lt;/DOCUMENT&gt;
&lt;/FILE&gt;`**Metadata and documents embedded**

`&lt;FILE&gt;
    &lt;DOCUMENT&gt;
        &lt;TEMPLATE&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="XXXXX" version="1"&gt;
&lt;payload&gt;PCFET0NUWVBFIGh0bWw+CjxodG1sPgoKPGhlYWQ+CiAgICA8bWV0YSBjaGFyc2V0PSJ1dGYtOCI+CiAgICA8bWV0YSBodHRwLWVxdWl2PSJYLVVBL
UNvbXBhdGlibGUiIGNvbnRlbnQ9IklFPWVkZ2UiPgogICAgPG1ldGEgbmFtZT0idmlld3BvcnQiIGNvbnRlbnQ9IndpZHRoPWRldmljZS13aWR0aCwgaW5pdGl
hbC1zY2FsZT0xLCBtYXhpbXVtLXNjYWxlPTEiPgogICAgPHRpdGxlPnB2aWRlb19hYTI1YWZiNTBjYmE0OTcwYjcxOTRkYjMyZTllNTBkYjwvdGl0bGU+CgogI
CAgPCEtLSBQbGF5ZXIgU3R5bGVzIC0tPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiB0eXBlPSJ0ZXh0L2NzcyIgaHJlZj0iaG9zdG5hbWUvcHZpZGVvLXB
sYXllci9nZXRBc3NldC92Mi9pdnAvc3R5bGVzL3BsYXllci5jc3MiPgogICAgPCEtLSBTa2luIFN0eWxlcyAtLT4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVld
CIgdHlwZT0idGV4dC9jc3MiIGhyZWY9Imhvc3RuYW1lL3B2aWRlby1wbGF5ZXIvZ2V0QXNzZXQvdjIvaXZwL3NraW5zL2RlZmF1bHQvc3R5bGVzL3NraW4uY3N
zIj4KICAgIDwhLS0galF1ZXJ5IGN1c3RvbSAoZS5nLnNsaWRlcikgLS0+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIHR5cGU9InRleHQvY3NzIiBocmVmP
SJob3N0bmFtZS9wdmlkZW8tcGxheWVyL2dldEFzc2V0L3YyL2xpYnMvanF1ZXJ5LXVpLmN1c3RvbS5taW4uY3NzIj4KCiAgICA8c2NyaXB0IHR5cGU9InRleHQ
vcGxhaW4iIGlkPSJkb2MtZGF0YSI+CnsiRklMRSI6eyJET0NVTUVOVCI6W3siQ2xpZW50Q29kZSI6IkFCQzAxIiwic2hpcG1lbnRJRCI6IjM0ODhiY2EyYzRmY
TQ4MjlhNzU2MjE3YjFlZWQ0NjViIiwiS2V5IjoidmJnMDAiLCJURU1QTEFURSI6W3siVFRTIjp7InNldHRpbmdzIjp7ImVudkRuIjoiZW52XHUwMDNkYmF0Y2g
tdGVzdDIsYnBcdTAwM2RwVmlkZW8gVmFsaWRhdGlvbixwcm9jXHUwMDNkUGFhcyBWYWxpZGF0aW9uLG91XHUwMDNkRE9YRUUscFx1MDAzZERveGVlIFBsYXRmb
3JtIiwiaGFzaFppcCI6ImIyZGRmYzM1NjkyYTFhMmFjNWY2MTViMzU2NGQ2MDhmNWUwYzk5YTU5ZDYxNjNmMzUxNjkxMDJkYWRmM2M1Y2IiLCJ0dHMtdXJsIjo
iIiwiZGF0YUhhc2giOiJkZDJiZDZhMGQ3NTJiZTE5ZWEyMGMyZTJmNzA0MTBmMzRiZTFmZWVmOTFlNTY3MjgwMGU2NjM1YzFjYTZkMzA5IiwiZG9jSUQiOiIzN
Dg4YmNhMmM0ZmE0ODI5YTc1NjIxN2IxZWVkNDY1YiIsInBhcnRuZXJJRCI6IkJ4eHpZYW1KbWQ5d3dnWkF2ZE8xOTE4Q28yQzNWaFZtIiwiYXV0aG9yaXphdGl
vbiI6ImYyYjZjMzViMzZhM2Q0ZjY5YTEwYzYyOTM0MDIzMmQ3YzNkZDBmOTAxNjdkYzU3MWYxNjgzOTIyZmVhNjYzMWYiLCJlbnYiOiJURVNUIiwiYXBwRG4iO
iJicFx1MDAzZHBWaWRlbyBWYWxpZGF0aW9uLHByb2NcdTAwM2RQYWFzIFZhbGlkYXRpb24sb3VcdTAwM2RET1hFRSxwXHUwMDNkRG94ZWUgUGxhdGZvcm0iLCJ
jYWNoaW5nIjp0cnVlfSwiZGF0YSI6W3siaWQiOiJUVFNfTUFMRTAxIiwiUGFyYW1ldGVycyI6eyJyYXRlIjoibWVkaXVtIiwicGFyYWdyYXBoQnJlYWsiOjY1M
Cwidm9sdW1lIjoibWVkaXVtIiwic2VudGVuY2VCcmVhayI6NTAwfSwiaW5wdXQiOnsiZGF0YSI6IkhpIE1hdHRlbywgSVx1MDAyN20gSm9leSBhbmQgSVx1MDA
yN20gdXNpbmcgYSBUVFMgdG8gdGFsayB0byB5b3UuIiwidHlwZSI6ImFwcGxpY2F0aW9uL3NzbWwreG1sIn0sInZvaWNlIjp7Im5hbWUiOiJKb2V5IiwiZ2VuZ
GVyIjoiTWFsZSIsImxhbmd1YWdlIjoiZW4tVVMifSwib3V0cHV0Rm9ybWF0Ijp7InNhbXBsZVJhdGUiOjIyMDUwfX0seyJpZCI6IlRUU19GRU1BTEUwMSIsIlB
hcmFtZXRlcnMiOnsicmF0ZSI6Im1lZGl1bSIsInBhcmFncmFwaEJyZWFrIjo2NTAsInZvbHVtZSI6Im1lZGl1bSIsInNlbnRlbmNlQnJlYWsiOjUwMH0sImluc
HV0Ijp7ImRhdGEiOiJIb2xhIE1hdHRlbyBzb3kgQ29uY2hpdGEgeSBlc3RveSB1c2FuZG8gdW4gVFRTIHBhcmEgaGFibGFyIGNvbnRpZ28uIiwidHlwZSI6ImF
wcGxpY2F0aW9uL3NzbWwreG1sIn0sInZvaWNlIjp7Im5hbWUiOiJDb25jaGl0YSIsImdlbmRlciI6IkZlbWFsZSIsImxhbmd1YWdlIjoiZXMtRVMifSwib3V0c
HV0Rm9ybWF0Ijp7InNhbXBsZVJhdGUiOjIyMDUwfX0seyJpZCI6IlRUU19NQUxFMDMtMDEiLCJQYXJhbWV0ZXJzIjp7InJhdGUiOiJtZWRpdW0iLCJwYXJhZ3J
hcGhCcmVhayI6NjUwLCJ2b2x1bWUiOiJtZWRpdW0iLCJzZW50ZW5jZUJyZWFrIjo1MDB9LCJpbnB1dCI6eyJkYXRhIjoiVXNpbmcgVFRTIGZyYW1lIHN5bmMge
W91IGNhbiBtYWtlIHRoZSB2b2ljZSBzdGFydCBhdCBhbiBleGFjdCBmcmFtZSIsInR5cGUiOiJhcHBsaWNhdGlvbi9zc21sK3htbCJ9LCJ2b2ljZSI6eyJuYW1
lIjoiSm9leSIsImdlbmRlciI6Ik1hbGUiLCJsYW5ndWFnZSI6ImVuLVVTIn0sIm91dHB1dEZvcm1hdCI6eyJzYW1wbGVSYXRlIjoyMjA1MH19LHsiaWQiOiJUV
FNfRkVNQUxFMDMtMDIiLCJQYXJhbWV0ZXJzIjp7InJhdGUiOiJtZWRpdW0iLCJwYXJhZ3JhcGhCcmVhayI6NjUwLCJ2b2x1bWUiOiJtZWRpdW0iLCJzZW50ZW5
jZUJyZWFrIjo1MDB9LCJpbnB1dCI6eyJkYXRhIjoiU8OtLCBlc28gZXMgc2luIGR1ZGEgw7p0aWwgcGFyYSBzaW5jcm9uaXphciBUVFMgYSBhbmltYWNpw7NuI
iwidHlwZSI6ImFwcGxpY2F0aW9uL3NzbWwreG1sIn0sInZvaWNlIjp7Im5hbWUiOiJDb25jaGl0YSIsImdlbmRlciI6IkZlbWFsZSIsImxhbmd1YWdlIjoiZXM
tRVMifSwib3V0cHV0Rm9ybWF0Ijp7InNhbXBsZVJhdGUiOjIyMDUwfX1dfSwiQ1VTVE9NRVJfREFUQSI6W3siVFRTIjpbe31dLCJEQVRBIjpbeyJ2aWRlb0JhY
2tncm91bmRTY2VuZTEiOiJ2aWRlb3MvQkdTY2VuZUlELm1wNCIsImd1aWQiOiJhYTI1YWZiNTBjYmE0OTcwYjcxOTRkYjMyZTllNTBkYiIsImxhc3ROYW1lIjo
iRG9sbGEiLCJlbWFpbCI6Im1kb2xsYUBkb3hlZS5jb20iLCJhZGRyZXNzIjoiWFkiLCJDbGllbnRGaXNjYWxDb2RlIjo5MTAwMiwiZmlyc3ROYW1lIjoiTWF0d
GVvIiwiQWN0aXZhdGlvbkRhdGUiOjIwMTUxMjE1LCJkb2N1bWVudENsYXNzIjoiUEVSU19WSURFTyIsIkRlbGl2ZXJ5UHJvZHVjdCI6Mn1dLCJTQ0VORVMiOls
iU0NFTkUxIiwiU0NFTkUyIiwiU0NFTkUzIl19XX1dLCJob3N0TmFtZSI6Imh0dHBzOi8vdGVzdDIuZGV2LmRveGVlLmNvbSJ9XX19ICA8L3NjcmlwdD4KCiAgI
CA8c2NyaXB0IHR5cGU9InRleHQvcGxhaW4iIGlkPSJkb2MtcHVybCI+Cgl7CgkJImJhc2UtdXJsIgk6IAoJCSJtYXN0ZXItZmlsZSIJOiAicFZpZGVvLmh0bWw
iIAoJfQogIDwvc2NyaXB0PgoKICAgIDxzY3JpcHQgdHlwZT0idGV4dC9wbGFpbiIgaWQ9InBsYXllci1vcHRpb25zIj4KCXsKCQkib3B0aW9ucyIJOiAKCQl7C
gkJfSwKCQkiaXNBbmFseXRpY3NFbmFibGVkIjogdHJ1ZQoJfQogIDwvc2NyaXB0PgoKICAgIDxzY3JpcHQgdHlwZT0idGV4dC9wbGFpbiIgaWQ9InBsYXllci1
lbnYiPgp7CiAgImRveGVlUGxhdGZvcm1JZCI6ICJ0ZXN0Mi5kZXYuZG94ZWUuY29tIiwKICAiYW5hbHl0aWNzVXJsIjogIiIsCiAgInNjb3BlIjogIlRFU1QiL
AogICJzaGlwbWVudElkIjogIjM0ODhiY2EyYzRmYTQ4MjlhNzU2MjE3YjFlZWQ0NjViIiwKICAic29mdHdhcmVTZXJ2aWNlIjogIkJBVENIIiwKICAiYXBwbGl
jYXRpb25OYW1lIjogInBWaWRlbyBWYWxpZGF0aW9uIiwKICAiY2xpZW50TmFtZSI6ICJET1hFRSIsCiAgImVudmlyb25tZW50TmFtZSI6ICJiYXRjaC10ZXN0M
iIsCiAgInByb2NlZHVyZU5hbWUiOiAiUGFhcyBWYWxpZGF0aW9uIgp9ICA8L3NjcmlwdD4KPC9oZWFkPgoKPGJvZHk+Cgo8IS0tIFBsYXllciAtLT4KPGRpdiB
pZD0icGxheWVyIj48L2Rpdj4KCgoKCjwhLS0gTm9uIGJsb2NraW5nIEphdmFTY3JpcHQgLS0+CjxzY3JpcHQgc3JjPSJob3N0bmFtZS9wdmlkZW8tcGxheWVyL
2dldEFzc2V0L3YyL2xpYnMvZGVwZW5kZW5jaWVzLm1pbi5qcyIgdHlwZT0idGV4dC9qYXZhc2NyaXB0Ij48L3NjcmlwdD4KPHNjcmlwdCBzcmM9Imhvc3RuYW1
lL3B2aWRlby1wbGF5ZXIvZ2V0QXNzZXQvdjIvbGlicy9pdnAubWluLmpzIiB0eXBlPSJ0ZXh0L2phdmFzY3JpcHQiPjwvc2NyaXB0Pgo8c2NyaXB0PgogICAgb
mV3IERveGVlUGxheWVyKHsKICAgICAgICByb290U2VsZWN0b3I6ICcjcGxheWVyJywKICAgICAgICBkb2NEYXRhOiAgICAgICcjZG9jLWRhdGEnLAogICAgICA
gIGRvY1B1cmw6ICAgICAgJyNkb2MtcHVybCcsCiAgICAgICAgcGxheWVyRW52OiAJICAnI3BsYXllci1lbnYnLAogICAgICAgIHBsYXllck9wdGlvbnM6JyNwb
GF5ZXItb3B0aW9ucycKICAgIH0pOwo8L3NjcmlwdD4KCjwvYm9keT4KCjwvaHRtbD4K&lt;/payload&gt;
                &lt;metadata ID="BP-107001-0000000001231198-6" firstName="XXXXX" lastName="XXXXX" version="1"/&gt;
            &lt;/DA&gt;
        &lt;/TEMPLATE&gt;
    &lt;/DOCUMENT&gt;
    &lt;DOCUMENT&gt;
        &lt;TEMPLATE&gt;
            &lt;DA docCategory="GENERIC_CLASS" firstName="YYYYY" version="2"&gt;
&lt;payload&gt;PCFET0NUWVBFIGh0bWw+CjxodG1sPgoKPGhlYWQ+CiAgICA8bWV0YSBjaGFyc2V0PSJ1dGYtOCI+CiAgICA8bWV0YSBodHRwLWVxdWl2PSJYLVVBL
UNvbXBhdGlibGUiIGNvbnRlbnQ9IklFPWVkZ2UiPgogICAgPG1ldGEgbmFtZT0idmlld3BvcnQiIGNvbnRlbnQ9IndpZHRoPWRldmljZS13aWR0aCwgaW5pdGl
hbC1zY2FsZT0xLCBtYXhpbXVtLXNjYWxlPTEiPgogICAgPHRpdGxlPnB2aWRlb19jNTEwN2M1MTI0NDY0NjNhOWMxODVhNTRkMzcyOGI3MzwvdGl0bGU+CgogI
CAgPCEtLSBQbGF5ZXIgU3R5bGVzIC0tPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiB0eXBlPSJ0ZXh0L2NzcyIgaHJlZj0iaG9zdG5hbWUvcHZpZGVvLXB
sYXllci9nZXRBc3NldC92Mi9pdnAvc3R5bGVzL3BsYXllci5jc3MiPgogICAgPCEtLSBTa2luIFN0eWxlcyAtLT4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVld
CIgdHlwZT0idGV4dC9jc3MiIGhyZWY9Imhvc3RuYW1lL3B2aWRlby1wbGF5ZXIvZ2V0QXNzZXQvdjIvaXZwL3NraW5zL2RlZmF1bHQvc3R5bGVzL3NraW4uY3N
zIj4KICAgIDwhLS0galF1ZXJ5IGN1c3RvbSAoZS5nLnNsaWRlcikgLS0+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIHR5cGU9InRleHQvY3NzIiBocmVmP
SJob3N0bmFtZS9wdmlkZW8tcGxheWVyL2dldEFzc2V0L3YyL2xpYnMvanF1ZXJ5LXVpLmN1c3RvbS5taW4uY3NzIj4KCiAgICA8c2NyaXB0IHR5cGU9InRleHQ
vcGxhaW4iIGlkPSJkb2MtZGF0YSI+CnsiRklMRSI6eyJET0NVTUVOVCI6W3siQ2xpZW50Q29kZSI6IkFCQzAxIiwic2hpcG1lbnRJRCI6IjVhNjczOGIwNGExN
DQwMzU5ZjFhODdkNGJhYTkyY2QzIiwiS2V5IjoidWRzMDAiLCJURU1QTEFURSI6W3siVFRTIjp7InNldHRpbmdzIjp7ImVudkRuIjoiZW52XHUwMDNkYmF0Y2g
tdGVzdDIsYnBcdTAwM2RwVmlkZW8gVmFsaWRhdGlvbixwcm9jXHUwMDNkUGFhcyBWYWxpZGF0aW9uLG91XHUwMDNkRE9YRUUscFx1MDAzZERveGVlIFBsYXRmb
3JtIiwiaGFzaFppcCI6IjQ3ODk1N2NlZWYyODBiMzVmNWVjOTUzNTllNThjYWIwNzMxMjgzZTdmYjg5M2M0ZWI1MzI0NWQ0NzkzNmEyZWMiLCJ0dHMtdXJsIjo
iIiwiZGF0YUhhc2giOiJkZDJiZDZhMGQ3NTJiZTE5ZWEyMGMyZTJmNzA0MTBmMzRiZTFmZWVmOTFlNTY3MjgwMGU2NjM1YzFjYTZkMzA5IiwiZG9jSUQiOiI1Y
TY3MzhiMDRhMTQ0MDM1OWYxYTg3ZDRiYWE5MmNkMyIsInBhcnRuZXJJRCI6IkJ4eHpZYW1KbWQ5d3dnWkF2ZE8xOTE4Q28yQzNWaFZtIiwiYXV0aG9yaXphdGl
vbiI6IjI0NzRmNzNkOGNmMWMxNTdkYjJkNGE1YWNlYzQzNzFlOGMxNDc3Yzg3NTgyNTk5N2RiZGNhMTBlYjU0MTFjZjkiLCJlbnYiOiJURVNUIiwiYXBwRG4iO
iJicFx1MDAzZHBWaWRlbyBWYWxpZGF0aW9uLHByb2NcdTAwM2RQYWFzIFZhbGlkYXRpb24sb3VcdTAwM2RET1hFRSxwXHUwMDNkRG94ZWUgUGxhdGZvcm0iLCJ
jYWNoaW5nIjp0cnVlfSwiZGF0YSI6W3siaWQiOiJUVFNfTUFMRTAxIiwiUGFyYW1ldGVycyI6eyJyYXRlIjoibWVkaXVtIiwicGFyYWdyYXBoQnJlYWsiOjY1M
Cwidm9sdW1lIjoibWVkaXVtIiwic2VudGVuY2VCcmVhayI6NTAwfSwiaW5wdXQiOnsiZGF0YSI6IkhpIE1hdHRlbywgSVx1MDAyN20gSm9leSBhbmQgSVx1MDA
yN20gdXNpbmcgYSBUVFMgdG8gdGFsayB0byB5b3UuIiwidHlwZSI6ImFwcGxpY2F0aW9uL3NzbWwreG1sIn0sInZvaWNlIjp7Im5hbWUiOiJKb2V5IiwiZ2VuZ
GVyIjoiTWFsZSIsImxhbmd1YWdlIjoiZW4tVVMifSwib3V0cHV0Rm9ybWF0Ijp7InNhbXBsZVJhdGUiOjIyMDUwfX0seyJpZCI6IlRUU19GRU1BTEUwMSIsIlB
hcmFtZXRlcnMiOnsicmF0ZSI6Im1lZGl1bSIsInBhcmFncmFwaEJyZWFrIjo2NTAsInZvbHVtZSI6Im1lZGl1bSIsInNlbnRlbmNlQnJlYWsiOjUwMH0sImluc
HV0Ijp7ImRhdGEiOiJIb2xhIE1hdHRlbyBzb3kgQ29uY2hpdGEgeSBlc3RveSB1c2FuZG8gdW4gVFRTIHBhcmEgaGFibGFyIGNvbnRpZ28uIiwidHlwZSI6ImF
wcGxpY2F0aW9uL3NzbWwreG1sIn0sInZvaWNlIjp7Im5hbWUiOiJDb25jaGl0YSIsImdlbmRlciI6IkZlbWFsZSIsImxhbmd1YWdlIjoiZXMtRVMifSwib3V0c
HV0Rm9ybWF0Ijp7InNhbXBsZVJhdGUiOjIyMDUwfX0seyJpZCI6IlRUU19NQUxFMDMtMDEiLCJQYXJhbWV0ZXJzIjp7InJhdGUiOiJtZWRpdW0iLCJwYXJhZ3J
hcGhCcmVhayI6NjUwLCJ2b2x1bWUiOiJtZWRpdW0iLCJzZW50ZW5jZUJyZWFrIjo1MDB9LCJpbnB1dCI6eyJkYXRhIjoiVXNpbmcgVFRTIGZyYW1lIHN5bmMge
W91IGNhbiBtYWtlIHRoZSB2b2ljZSBzdGFydCBhdCBhbiBleGFjdCBmcmFtZSIsInR5cGUiOiJhcHBsaWNhdGlvbi9zc21sK3htbCJ9LCJ2b2ljZSI6eyJuYW1
lIjoiSm9leSIsImdlbmRlciI6Ik1hbGUiLCJsYW5ndWFnZSI6ImVuLVVTIn0sIm91dHB1dEZvcm1hdCI6eyJzYW1wbGVSYXRlIjoyMjA1MH19LHsiaWQiOiJUV
FNfRkVNQUxFMDMtMDIiLCJQYXJhbWV0ZXJzIjp7InJhdGUiOiJtZWRpdW0iLCJwYXJhZ3JhcGhCcmVhayI6NjUwLCJ2b2x1bWUiOiJtZWRpdW0iLCJzZW50ZW5
jZUJyZWFrIjo1MDB9LCJpbnB1dCI6eyJkYXRhIjoiU8OtLCBlc28gZXMgc2luIGR1ZGEgw7p0aWwgcGFyYSBzaW5jcm9uaXphciBUVFMgYSBhbmltYWNpw7NuI
iwidHlwZSI6ImFwcGxpY2F0aW9uL3NzbWwreG1sIn0sInZvaWNlIjp7Im5hbWUiOiJDb25jaGl0YSIsImdlbmRlciI6IkZlbWFsZSIsImxhbmd1YWdlIjoiZXM
tRVMifSwib3V0cHV0Rm9ybWF0Ijp7InNhbXBsZVJhdGUiOjIyMDUwfX1dfSwiQ1VTVE9NRVJfREFUQSI6W3siVFRTIjpbe31dLCJEQVRBIjpbeyJ2aWRlb0JhY
2tncm91bmRTY2VuZTEiOiJ2aWRlb3MvQkdTY2VuZUlELm1wNCIsImd1aWQiOiJjNTEwN2M1MTI0NDY0NjNhOWMxODVhNTRkMzcyOGI3MyIsImxhc3ROYW1lIjo
iRG9sbGEiLCJlbWFpbCI6Im1kb2xsYUBkb3hlZS5jb20iLCJhZGRyZXNzIjoiWFkiLCJDbGllbnRGaXNjYWxDb2RlIjo5MTAwMiwiZmlyc3ROYW1lIjoiTWF0d
GVvIiwiQWN0aXZhdGlvbkRhdGUiOjIwMTUxMjE1LCJkb2N1bWVudENsYXNzIjoiUEVSU19WSURFTyIsIkRlbGl2ZXJ5UHJvZHVjdCI6Mn1dLCJTQ0VORVMiOls
iU0NFTkUxIiwiU0NFTkUyIiwiU0NFTkUzIl19XX1dLCJob3N0TmFtZSI6Imh0dHBzOi8vdGVzdDIuZGV2LmRveGVlLmNvbSJ9XX19ICA8L3NjcmlwdD4KCiAgI
CA8c2NyaXB0IHR5cGU9InRleHQvcGxhaW4iIGlkPSJkb2MtcHVybCI+Cgl7CgkJImJhc2UtdXJsIgk6IAoJCSJtYXN0ZXItZmlsZSIJOiAicFZpZGVvLmh0bWw
iIAoJfQogIDwvc2NyaXB0PgoKICAgIDxzY3JpcHQgdHlwZT0idGV4dC9wbGFpbiIgaWQ9InBsYXllci1vcHRpb25zIj4KCXsKCQkib3B0aW9ucyIJOiAKCQl7C
gkJfSwKCQkiaXNBbmFseXRpY3NFbmFibGVkIjogdHJ1ZQoJfQogIDwvc2NyaXB0PgoKICAgIDxzY3JpcHQgdHlwZT0idGV4dC9wbGFpbiIgaWQ9InBsYXllci1
lbnYiPgp7CiAgImRveGVlUGxhdGZvcm1JZCI6ICJ0ZXN0Mi5kZXYuZG94ZWUuY29tIiwKICAiYW5hbHl0aWNzVXJsIjogIiIsCiAgInNjb3BlIjogIlRFU1QiL
AogICJzaGlwbWVudElkIjogIjVhNjczOGIwNGExNDQwMzU5ZjFhODdkNGJhYTkyY2QzIiwKICAic29mdHdhcmVTZXJ2aWNlIjogIkJBVENIIiwKICAiYXBwbGl
jYXRpb25OYW1lIjogInBWaWRlbyBWYWxpZGF0aW9uIiwKICAiY2xpZW50TmFtZSI6ICJET1hFRSIsCiAgImVudmlyb25tZW50TmFtZSI6ICJiYXRjaC10ZXN0M
iIsCiAgInByb2NlZHVyZU5hbWUiOiAiUGFhcyBWYWxpZGF0aW9uIgp9ICA8L3NjcmlwdD4KPC9oZWFkPgoKPGJvZHk+Cgo8IS0tIFBsYXllciAtLT4KPGRpdiB
pZD0icGxheWVyIj48L2Rpdj4KCgoKCjwhLS0gTm9uIGJsb2NraW5nIEphdmFTY3JpcHQgLS0+CjxzY3JpcHQgc3JjPSJob3N0bmFtZS9wdmlkZW8tcGxheWVyL
2dldEFzc2V0L3YyL2xpYnMvZGVwZW5kZW5jaWVzLm1pbi5qcyIgdHlwZT0idGV4dC9qYXZhc2NyaXB0Ij48L3NjcmlwdD4KPHNjcmlwdCBzcmM9Imhvc3RuYW1
lL3B2aWRlby1wbGF5ZXIvZ2V0QXNzZXQvdjIvbGlicy9pdnAubWluLmpzIiB0eXBlPSJ0ZXh0L2phdmFzY3JpcHQiPjwvc2NyaXB0Pgo8c2NyaXB0PgogICAgb
mV3IERveGVlUGxheWVyKHsKICAgICAgICByb290U2VsZWN0b3I6ICcjcGxheWVyJywKICAgICAgICBkb2NEYXRhOiAgICAgICcjZG9jLWRhdGEnLAogICAgICA
gIGRvY1B1cmw6ICAgICAgJyNkb2MtcHVybCcsCiAgICAgICAgcGxheWVyRW52OiAJICAnI3BsYXllci1lbnYnLAogICAgICAgIHBsYXllck9wdGlvbnM6JyNwb
GF5ZXItb3B0aW9ucycKICAgIH0pOwo8L3NjcmlwdD4KCjwvYm9keT4KCjwvaHRtbD4K&lt;/payload&gt;
                &lt;metadata ID="BP-107001-0000000001231198-5" firstName="YYYYY" lastName="YYYYY" version="2"/&gt;
            &lt;/DA&gt;
        &lt;/TEMPLATE&gt;
    &lt;/DOCUMENT&gt;
&lt;/FILE&gt;`## Retrieve the Latest Document for a Given Clause During Extraction
The following procedure explains how to extract a document from Digital Archiving 3 based on the minimum or maximum value of a searchable index, without having to specify a set value.

In order to extract a document based on the minimum (or maximum) value of a searchable index, use "$MIN" (or "$MAX") as the value for the desired index in the extraction query.

> Note

The placeholders "$MIN" and "$MAX" are only applicable to number, date and time data types. These value placeholders are not applicable to string or clob data types.

> Important

It is only possible to specify one "$MIN" or "$MAX" value for each **DA **tag in the input XML file.

Each search query may contain at most one "$MIN" or "$MAX" value placeholder. The search query that contains the "$MIN" or "$MAX" value placeholder may return at most one document.

### Examples
#### $MAX value extraction
To retrieve the latest document (i.e. the document with the highest version number), configure the input XML file as follows:

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;FILE&gt;
&lt;DOCUMENT&gt;
&lt;TEMPLATE name="default"&gt;
&lt;DA CUSTOMER_CODE="CC0001" INVOICE_NUM="AB00001" ISSUE_DATE="2019-10-30" VERSION="$MAX" docCategory="
CATEGORY" /&gt;
&lt;/TEMPLATE&gt;
&lt;/DOCUMENT&gt;
&lt;/FILE&gt;`#### $MIN value extraction
To retrieve the oldest document (i.e. the document with the lowest version number), configure the input XML file as follows:

`&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;FILE&gt;
&lt;DOCUMENT&gt;
&lt;TEMPLATE name="default"&gt;
&lt;DA CUSTOMER_CODE="CC0001" INVOICE_NUM="AB00001" ISSUE_DATE="2019-10-30" VERSION="$MIN" docCategory="
CATEGORY" /&gt;
&lt;/TEMPLATE&gt;
&lt;/DOCUMENT&gt;
&lt;/FILE&gt;`

 p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;}  p[data-block-id]:empty::after {content: "\00A0";}