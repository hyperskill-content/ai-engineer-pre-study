# Python Readiness Checklist

This checklist covers the Python you need to start the AI Engineering cohort comfortably. In the course you'll write code that calls model APIs and works with the JSON they return, often sending many requests at once. Every topic below comes up in that code.

Nothing here is graded and nobody checks your answers. Use the list to find out what you already know and what to study before the cohort starts.

## How to use it

Each topic has a short task underneath it.

1. Read each task and tick the box if you could do it without looking anything up, apart from a quick syntax check. If you understand the idea but have never written the code yourself, leave the box empty.
2. For every empty box, work through the matching part of the notebook linked at the top of that section. You can skip any section where all the boxes are ticked.
3. Go through the list again before the cohort starts. By the first day, every box should be ticked.

To track your progress, copy this file somewhere you can edit it (a fork of this repo, a local clone, or your notes) and change `[ ]` to `[x]` as you go.

## Part 1: Python for working with data and APIs

The topics in this part are covered in the [Intro to Python notebook](https://github.com/hyperskill-content/Python_intro/blob/main/notebooks/Python_Intro_Preliminary.ipynb).

- [ ] String formatting with f-strings for prompt construction\
  Build a multi-line prompt from variables, with expressions and format specifiers inside `{}`.
- [ ] Dictionaries and lists that map to JSON structures\
  Predict which Python `dict`s and `list`s a given JSON document turns into, and convert between the two with the `json` module.
- [ ] Nested data structures for API payloads\
  Create a payload such as a list of message dicts with several fields each, then read and update values a few levels deep.
- [ ] Functions with type hints and default parameters\
  Write a function with annotated parameters and a return type, then call it with keyword arguments that override its defaults.
- [ ] List comprehensions and filtering\
  Rewrite a loop that filters or transforms items as a comprehension, and tell when the plain loop is easier to read.
- [ ] Control flow and error handling\
  Use `if`/`elif`/`else`, `for`, and `while`, and catch specific exceptions with `try`/`except`/`else`/`finally` rather than a bare `except`.
- [ ] Lambda functions and sorting\
  Sort a list of dicts by one or more keys with `sorted(..., key=lambda ...)`, in ascending and descending order.
- [ ] Working with API response structures\
  Take an unfamiliar JSON response, find the field you need, and extract it safely (for example with `.get()`) when some keys may be missing.

## Part 2: HTTP requests and async

The topics in this part are covered in the [HTTP and Async notebook](https://github.com/hyperskill-content/Python_intro/blob/main/notebooks/HTTP_async.ipynb).

- [ ] HTTP requests with the `requests` library\
  Install `requests`, call a public API, and inspect the response object.
- [ ] GET/POST/PUT/DELETE methods\
  Explain what each method is for and send each one with `requests`.
- [ ] Query parameters and request bodies\
  Pass query parameters with `params=`, send a JSON body with `json=`, and set headers such as an API key with `headers=`.
- [ ] Response handling (status codes, JSON parsing, headers)\
  Check `status_code` or call `raise_for_status()`, parse the body with `.json()`, and read the response headers.
- [ ] Sessions and context managers\
  Reuse one `requests.Session` across several calls, and explain what a `with` block takes care of.
- [ ] Async programming with async/await\
  Write an `async def` function, run it with `asyncio.run()`, and explain why `await` is needed and where it is allowed.
- [ ] `aiohttp` for concurrent requests\
  Make HTTP requests with `aiohttp.ClientSession` inside an async function.
- [ ] `asyncio.gather()` for parallel execution\
  Start many requests at once with `asyncio.gather()`, collect the results in order, and decide what happens when one of them fails.
- [ ] Rate limiting and error handling in async contexts\
  Limit how many requests run at the same time (for example with `asyncio.Semaphore`) and retry failed requests after a delay.

When every box is ticked, continue with the [rest of the pre-study materials](../README.md).
