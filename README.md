# Coding Interview: AI-Assisted Engineering Evaluation

You may use an AI coding assistant during this exercise.

Build a small service that accepts a list of job postings and returns the Top K most relevant jobs for a user query.

## Example input

```json
{
  "query": "senior backend engineer with Kafka and distributed systems",
  "k": 3,
  "jobs": [
    {
      "id": "1",
      "title": "Backend Engineer",
      "description": "Build distributed systems using Kafka and Go"
    }
  ]
}
```

## Requirements

- Return the top `k` jobs ranked by relevance.
- Start with a simple deterministic implementation; AI/embeddings may be added if justified.
- Handle invalid input and edge cases.
- Include tests.
- Explain the time and space complexity.

You may ask AI to generate, refactor, debug, or test code. **You are responsible for verifying everything the AI produces.**

## During the interview, explain

- What you asked the AI to do and why.
- Which AI-generated suggestions you accepted or rejected.
- How you verified correctness.
- What bugs or weaknesses you found in the AI output.
- What tests you added that the AI did not initially consider.
- How you would evaluate an AI/embedding-based relevance implementation before deploying it.
- What you would change for 10 million jobs instead of 100.

## Dataset

`jobs.json` contains **1,000 real job postings** sampled from a production job board. Each entry has the shape:

```json
{
  "id": "uuid",
  "title": "string",
  "company": "string | null",
  "location": "string | null",
  "remote": "boolean | null",
  "seniority": "string | null",
  "description": "string (plain text, HTML stripped)"
}
```

Use it as the `jobs` input for larger-scale testing (relevance quality, latency, memory). For the API contract you implement, the `jobs` array in the request body is still the source of truth — the file is provided so you don't have to invent test data.

## Getting started

Pick any language and framework. There is no starter code — part of the exercise is deciding the shape of the service.

Suggested first commit: a working endpoint that returns top-k by a trivial scorer (e.g. keyword overlap), with one happy-path test. Iterate from there.
