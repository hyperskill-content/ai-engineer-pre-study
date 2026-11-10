# Python Readiness Checklist

This checklist lists the Python topics you need to start the AI Engineering cohort comfortably. Throughout the course you will write Python that builds prompts, sends requests to model APIs, and processes JSON responses, often many requests at once. Every item below shows up in that work.

It is a self-assessment, not a test. Nothing here is graded, and nobody checks your answers. Use it to see what you already know and what to study before the cohort starts, so you don't have to guess.

## How to use it

1. **Go through each item honestly.** Under each topic is a short description of what "knowing it" means. Tick the box only if you could do that without looking it up, or with only a quick check of the syntax.
2. **Mark what you're unsure about.** Anything you can't tick is what you should study. If you can explain a topic but haven't written the code yourself, leave it unticked.
3. **Study the gaps.** Each section links to the notebook that covers its topics. Work through the parts that match your unticked items. If you already know a section well, you can skip it.
4. **Come back to it.** Go through the checklist again before the cohort starts. Aim to have every box ticked by day one.

To keep track of your progress, copy this file somewhere you can edit it (a fork of this repo, a local clone, or your notes app) and replace `[ ]` with `[x]` as you go.

---

## Part 1: Python for working with data and APIs

Covered in the [Intro to Python notebook](https://github.com/hyperskill-content/Python_intro/blob/main/notebooks/Python_Intro_Preliminary.ipynb).

- [ ] **String formatting with f-strings for prompt construction**
  You can build a multi-line prompt from variables, using expressions and format specifiers inside `{}`.
- [ ] **Dictionaries and lists that map to JSON structures**
  You can predict how a JSON object or array turns into Python `dict`s and `list`s, and convert between them with the `json` module.
- [ ] **Nested data structures for API payloads**
  You can build a payload such as a list of message dicts, each with its own fields, and read or update values several levels deep.
- [ ] **Functions with type hints and default parameters**
  You can write a function with annotated parameters and a return type, and call it with keyword arguments that override the defaults.
- [ ] **List comprehensions and filtering**
  You can turn a loop that transforms or filters items into a single comprehension, and you know when a plain loop is easier to read.
- [ ] **Control flow and error handling**
  You can use `if`/`elif`/`else`, `for`, and `while`, and you can catch specific exceptions with `try`/`except`/`else`/`finally` instead of a bare `except`.
- [ ] **Lambda functions and sorting**
  You can sort a list of dicts by one or more keys with `sorted(..., key=lambda ...)`, including in reverse order.
- [ ] **Working with API response structures**
  Given an unfamiliar JSON response, you can find the field you need and extract it safely (for example with `.get()`), even when some keys may be missing.

## Part 2: HTTP requests and async

Covered in the [HTTP and Async notebook](https://github.com/hyperskill-content/Python_intro/blob/main/notebooks/HTTP_async.ipynb).

- [ ] **HTTP requests with the `requests` library**
  You can install `requests`, make a request to a public API, and inspect what came back.
- [ ] **GET/POST/PUT/DELETE methods**
  You know what each method is for and can make each one with `requests`.
- [ ] **Query parameters and request bodies**
  You can pass query parameters with `params=`, send a JSON body with `json=`, and add headers such as an API key with `headers=`.
- [ ] **Response handling (status codes, JSON parsing, headers)**
  You can check `status_code` or call `raise_for_status()`, parse the body with `.json()`, and read response headers.
- [ ] **Sessions and context managers**
  You can reuse a `requests.Session` for several calls and explain what the `with` statement does for you.
- [ ] **Async programming with async/await**
  You can write and run an `async def` function with `asyncio.run()`, and explain why `await` is needed and where you're allowed to use it.
- [ ] **`aiohttp` for concurrent requests**
  You can make HTTP requests with `aiohttp.ClientSession` inside an async function.
- [ ] **`asyncio.gather()` for parallel execution**
  You can start many requests at once with `asyncio.gather()`, collect their results in order, and decide what should happen when one of them fails.
- [ ] **Rate limiting and error handling in async contexts**
  You can cap the number of requests running at the same time (for example with `asyncio.Semaphore`) and retry failed requests with a delay between attempts.

---

**All boxes ticked?** You're ready on the Python side. Continue with the [rest of the pre-study materials](../README.md).
