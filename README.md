# GEO Guide for Healthcare Businesses — Cited By AI®

**A practical ASEO and GEO guide for GP practices, clinics, dentists,
physiotherapists, and specialist healthcare services.**
JSON-LD schema templates, CPS® content audit framework, and AI citation optimisation
for healthcare businesses seeking visibility in AI-generated answers.

---

## Why healthcare businesses are invisible in AI search

When a patient asks ChatGPT "best private GP clinic in Cheltenham" or Perplexity
"recommended physiotherapist near me accepting new patients", AI systems construct
answers from structured, citable sources. Most healthcare websites fail to appear
in these answers for three reasons: missing or incorrect JSON-LD schema, unstructured
service descriptions that AI cannot parse, and no specific clinical content
answering the questions patients ask AI most frequently.

A healthcare business with a well-optimised website can rank on page one of Google
and score an F on the Citation Probability Score® — meaning it is completely
invisible to AI search despite strong traditional SEO performance. These are
different retrieval mechanisms requiring different optimisation strategies.

---

## The correct schema types for healthcare businesses

| Business type | Correct schema type |
|---|---|
| GP practice or private clinic | `MedicalClinic` |
| Dental practice | `Dentist` |
| Physiotherapy practice | `Physiotherapy` |
| Optician | `Optician` |
| Hospital or specialist centre | `Hospital` |
| Individual healthcare professional | `Physician` or `MedicalBusiness` |

Using `LocalBusiness` for a healthcare practice is the most common schema error.
AI systems filter by schema type when answering healthcare discovery queries.
A dental practice using `LocalBusiness` will not appear for "dentist" queries
in AI-generated answers regardless of content quality.

---

## MedicalClinic schema template

```json
{
  "@context": "https://schema.org",
  "@type": "MedicalClinic",
  "name": "Your Clinic Name",
  "description": "Private [clinic type] in [city] offering [key services]. Serving patients across [area list]. [Accreditation or registration details]. New patients welcome. [Appointment availability — e.g. same-day appointments available].",
  "url": "https://yourwebsite.com",
  "telephone": "+44-000-000-0000",
  "email": "appointments@yourclinic.com",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Medical Centre",
    "addressLocality": "Your Town",
    "addressRegion": "Your County",
    "postalCode": "AA1 1AA",
    "addressCountry": "GB"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 00.0000,
    "longitude": -0.0000
  },
  "areaServed": [
    {
      "@type": "City",
      "name": "Your City"
    },
    {
      "@type": "AdministrativeArea",
      "name": "Nearby Town 1"
    },
    {
      "@type": "AdministrativeArea",
      "name": "Nearby Town 2"
    }
  ],
  "medicalSpecialty": [
    "General Practice",
    "Travel Medicine",
    "Minor Surgery",
    "Occupational Health"
  ],
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "08:00",
      "closes": "18:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Saturday",
      "opens": "09:00",
      "closes": "13:00"
    }
  ],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.9",
    "reviewCount": "213"
  },
  "potentialAction": {
    "@type": "ReserveAction",
    "name": "Book an appointment",
    "target": "https://yourwebsite.com/appointments"
  }
}
```

---

## Dentist schema template

```json
{
  "@context": "https://schema.org",
  "@type": "Dentist",
  "name": "Your Dental Practice Name",
  "description": "Independent dental practice in [city] offering NHS and private treatments. Services include general dentistry, cosmetic dentistry, orthodontics, and dental implants. Serving patients across [area list]. GDC registered. New NHS and private patients welcome.",
  "url": "https://yourwebsite.com",
  "telephone": "+44-000-000-0000",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Dental House",
    "addressLocality": "Your Town",
    "addressRegion": "Your County",
    "postalCode": "AA1 1AA",
    "addressCountry": "GB"
  },
  "areaServed": [
    {
      "@type": "City",
      "name": "Your City"
    },
    {
      "@type": "AdministrativeArea",
      "name": "Nearby Town"
    }
  ],
  "medicalSpecialty": [
    "General Dentistry",
    "Cosmetic Dentistry",
    "Orthodontics",
    "Dental Implants",
    "Teeth Whitening",
    "Invisalign"
  ],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.8",
    "reviewCount": "178"
  },
  "potentialAction": {
    "@type": "ReserveAction",
    "name": "Book a dental appointment",
    "target": "https://yourwebsite.com/book"
  }
}
```

---

## Why medicalSpecialty matters for healthcare AI citation

The `medicalSpecialty` field is the highest-impact schema addition for healthcare
businesses. AI systems answering "dentist specialising in Invisalign near [city]"
or "private GP offering same-day appointments in [area]" filter by medical
speciality signals. A generic `MedicalClinic` listing without `medicalSpecialty`
fields will be invisible for specialist queries even if the practice offers those
treatments every day. List every treatment, service, and specialism the business
genuinely provides.

---

## Why areaServed matters for healthcare AI citation

Patients frequently search for healthcare services across a wider geographic area
than their immediate town — particularly for specialist services. The `areaServed`
field makes a practice visible for surrounding area queries. A clinic in one town
with no `areaServed` field will not appear when patients in nearby towns search
for that service via AI systems.

---

## CPS® content framework for healthcare pages

### Homepage

The homepage should answer three AI queries in its opening 167 words:
what services the practice offers, where it is located, and whether it
is accepting new patients.

**Before (fails CPS® Answer Structure pillar):**
"Welcome to [Practice Name]. We are a dedicated team of healthcare professionals
committed to providing exceptional care to our patients. Our modern facilities
and experienced staff ensure you receive the highest standard of treatment..."

**After (passes CPS® Answer Structure pillar):**
"[Practice Name] is a private [clinic type] based in [City], serving patients
across [area list]. The clinic offers [top 3 services] with appointments
available from [next available date or timeframe]. [Accreditation details].
New patients are currently being accepted. Same-day appointments are available
for urgent consultations. All major private health insurers accepted."

The second version gives AI systems six facts to extract and cite. The first
contains no citable information in its opening sentences.

### Individual treatment and service pages

Each treatment page should open with a 134 to 167 word description structured as:

1. First sentence: what the treatment is, who it is for, and the practice name
2. Second sentence: what the treatment involves in plain, specific terms
3. Third sentence: cost or price range, appointment duration, and availability
4. Fourth sentence: how to book

### FAQ section

Every treatment page should include five to eight questions matching what
patients actually ask AI systems. Examples for a dental practice:

- "How much does Invisalign cost at [Practice Name]?"
- "Is [Practice Name] accepting new NHS patients?"
- "How long does a dental implant procedure take at [Practice Name]?"
- "Does [Practice Name] offer teeth whitening on the same day?"
- "What insurance does [Practice Name] accept?"

FAQ content has a significantly higher AI citation rate than standard prose
because the question-and-answer format matches how AI systems construct responses.

---

## Healthcare-specific GEO considerations

### NHS vs private distinction

AI systems answering "NHS dentist accepting new patients near [area]" and
"private GP clinic in [area]" are distinct queries requiring distinct content.
If the practice offers both NHS and private services, each should be explicitly
stated in schema and in page content. Mixing NHS and private information without
clear distinction reduces citation probability for both query types.

### Appointment availability signals

AI systems frequently receive queries about appointment availability —
"same-day GP appointment [city]", "emergency dental appointment [area]".
Include current availability signals in both schema and page content.
Update these regularly as outdated availability information reduces trust
and citation probability.

### Accreditation and registration signals

Healthcare accreditations and professional registrations are high-value
entity signals for AI systems. Include all relevant registrations in schema
and in visible page content:

- CQC registration number (for England)
- GDC registration (for dentists)
- GMC registration (for doctors)
- HCPC registration (for allied health professionals)
- Private health insurer accreditations

---

## The five most common healthcare GEO mistakes

**1. Using LocalBusiness instead of the correct healthcare schema type**
Replace `LocalBusiness` with `MedicalClinic`, `Dentist`, `Physiotherapy`,
or the appropriate type. This single change makes the practice eligible
for healthcare-specific discovery queries.

**2. No medicalSpecialty field**
Without `medicalSpecialty`, AI systems cannot match the practice to
specialist treatment queries. List every treatment and specialism explicitly.

**3. No areaServed field**
Healthcare practices serve patients across a wider geographic area than
their immediate location. Without `areaServed`, they are invisible for
surrounding area queries.

**4. No pricing or fee information**
AI systems answering "how much does [treatment] cost in [area]" need a
citable answer. Practices that publish fees or price ranges are cited
significantly more frequently for cost-related queries than those that
require contact before disclosing prices.

**5. No appointment availability information**
Availability is one of the most common patient queries to AI systems.
Practices that include availability signals — "new patients welcome",
"same-day appointments available" — are cited more frequently for
availability queries than those with no availability information.

---

## Frequently Asked Questions

**What is GEO for healthcare businesses?**

GEO (Generative Engine Optimisation) for healthcare is the practice of
structuring website content and schema markup so that AI systems —
including ChatGPT, Perplexity, and Google AI Overviews — can accurately
retrieve and cite the practice when patients ask AI for healthcare
recommendations. For healthcare businesses it focuses on three areas:
correct schema type, medical speciality signals, and CPS®-structured
content on treatment and service pages.

**How is healthcare GEO different from traditional healthcare SEO?**

Traditional healthcare SEO optimises for Google rankings using keyword
density, backlinks, and local directory listings. Healthcare GEO optimises
for AI citation using schema markup, structured treatment descriptions,
and medical speciality signals. A practice can rank on page one of Google
and be completely absent from ChatGPT and Perplexity answers for the same
query. Both require separate, parallel strategies.

**Are there any restrictions on healthcare content for AI citation?**

Healthcare content must be factually accurate and comply with relevant
professional and advertising standards (ASA, GMC, GDC guidelines in the UK).
AI systems cite healthcare content that is clear, specific, and factual.
Avoid promotional language and unsubstantiated claims — these reduce
citation probability and may breach professional advertising standards.

---

## Full CPS® Audit for Healthcare Businesses

The full CPS® audit for healthcare businesses covers:

- Per-block CPS® scores across homepage, treatment pages, and team pages
- Schema audit identifying incorrect types, missing fields, and markup errors
- Share of Voice measurement across ChatGPT, Perplexity, Google AI, Gemini, Copilot
- Hallucination detection — identifying where AI misrepresents the practice
- Competitor citation analysis — which local practices are being cited instead

Book a full audit: [citedbyai.info](https://citedbyai.info)

---

## Links

- 🌐 [citedbyai.info](https://citedbyai.info)
- 📋 [CPS® Framework](https://github.com/citedbyai/cps-framework)
- 💼 [LinkedIn](https://www.linkedin.com/in/citedbyai/)
- 🐦 [X / Twitter](https://x.com/citedbyai)

---

*CPS® (Citation Probability Score®) and Cited By AI® are registered trademarks of Cited By AI, United Kingdom.*
