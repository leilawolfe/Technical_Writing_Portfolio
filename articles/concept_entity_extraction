# Concept and Entity Extraction

## Introduction

Document extraction is the process of extracting structured data or attributes from unstructured documents such as invoices, contracts, and purchase orders. These attributes generally fall into two categories: *entities*, which are explicit values directly stated in the document, and *concepts*, which require interpretation or summarization. This distinction is important because entity extraction and concept extraction require different prompting strategies, evaluation methods, and quality metrics.


## Overview
| Characteristic | Entity Extraction | Concept Extraction |
| ----------------------- | --------------------- | ------------------------------------- |
| Output | Explicit value | Interpreted output |
| Examples | Dates, IDs, addresses | Clauses, obligations, renewal terms |
| Valid Outputs | Typically one | Potentially many |
| Evaluation | Exact comparison | Semantic evaluation or human review |


## Entity Extraction

Entity extraction identifies explicit values within a document. Examples include dates, document IDs, or billing addresses. Because the entities are explicitly stated in the document, there is typically only one correct value for each extracted entity. Generally speaking, entity extraction is straightforward to evaluate because the extracted value can be compared directly against a known ground truth (for example, comparing two dates or invoice numbers).

| Document Type | Text in Document | Entity to Extract | Extracted Value | Why It's an Entity |
| -------------- | ------------------------------------------------------- | --------------------- | ---------------------------------- | ------------------------------------------------------------------ |
| Invoice | "Invoice Date: March 15, 2026" | Invoice Date | March 15, 2026 | A single, deterministic date appearing in the document. | |
| Invoice | "Payment due within 30 days. Due Date: April 14, 2026." | Due Date | April 14, 2026 | A fixed payment deadline. |
| Contract | "This Agreement terminates on December 31, 2027." | Termination Date | December 31, 2027 | A specific contractual date with one correct answer. |
| Contract | "Vendor: Acme Manufacturing, Inc." | Vendor Name | Acme Manufacturing, Inc. | The legal name of the contracting party. |


## Concept Extraction

Concept extraction is the process of extracting attributes where some interpretation is necessary. These attributes may require summarization, or inference. As a result, multiple outputs may be correct even though they differ in wording or level of detail. For example, attributes that require summarization such as "termination clause" may produce different but equally valid summaries depending on how the original text is condensed. Not all concept extraction tasks produce summaries. Some produce discrete values although they require inference of the source text. For example, "Is this contract evergreen?" returns a discrete Yes/No response.

Concept extraction typically requires more iteration than entity extraction because success depends on both identifying relevant text and accurately interpreting its meaning. Additionally, a single attribute may have multiple valid interpretations or summaries. Consequently, the execution and evaluation of concept extraction are generally more challenging than entity extraction and should be accounted for when establishing delivery timelines.


| Document Type | Text in Document | Concept to Extract | Example Extracted Value | Why It's a Concept |
|---------------|------------------|--------------------|-------------------------|--------------------|
| Contract | "Either party may terminate this Agreement with 60 days' written notice." | Termination Clause | Either party may terminate the agreement by providing 60 days' written notice. | The model must interpret and summarize the legal language rather than copy a single value. |
| Contract | "Neither party shall be liable for delays caused by natural disasters, war, or government action." | Force Majeure | Performance obligations are suspended for events outside either party's control, such as natural disasters or war. | The model must interpret and summarize the legal language. |
| Contract | "This Agreement automatically renews for successive one-year terms unless either party provides 90 days' notice." | Renewal Terms | Automatically renews annually unless terminated with 90 days' notice. | The model synthesizes renewal behavior from the contract language. |
| Contract | "This Agreement shall automatically renew each year unless terminated by either party." | Is this contract evergreen? | Yes | A binary concept requiring interpretation instead of direct extraction. |


## Conclusion
In practice, most document processing solutions combine entity extraction and concept extraction to transform unstructured documents into structured, actionable data. Understanding the distinction between entity extraction and concept extraction helps set appropriate expectations for prompting strategies, evaluation approaches, project scope, and delivery timelines.
