### Hi there 👋
```python
import asyncio
import random
from itertools import count

cnt = count()
whoami = ["Simulation Engineer", "Python Developer", "Rust Enthusiast"]


async def describe(sth: str) -> str:
    await asyncio.sleep(random.random() / 10)
    print(sth)
    return sth


async def _main() -> None:
    print(f"Cycle {next(cnt)}: ")
    descriptions = [describe(me) for me in whoami]
    tasks = [asyncio.create_task(description) for description in descriptions]
    await asyncio.gather(*tasks)
    print()


async def main() -> None:
    while True:
        await _main()


if __name__ == "__main__":
    asyncio.run(main())
```
```
Cycle 0:
Simulation Engineer
Python Developer
Rust Enthusiast

Cycle 1:
Rust Enthusiast
Simulation Engineer
Python Developer

Cycle 2:
Python Developer
Rust Enthusiast
Simulation Engineer
...
```


<!--
**jrycw/jrycw** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
