# Ocean Apocalypse's Usage of CI
> [!NOTE]
> These are internal guides, not applying to people outside the organization. Contributors, however, should follow these additional recommendations.

At Ocean Apocalypse, we use CI for building, testing, analyzing and, sometimes, releasing software. However, there are some rules that we believe have to be established.

---

## Runner Usage
- **Prefer Ubuntu and Ubuntu Slim over the other runners:** Ubuntu is cheaper and, unless your workflow only runs on Windows or macOS, there's no real benefit to using the others.
- **Prefer Windows over macOS:** if Ubuntu is out of the question, prefer Windows over macOS. Despite Windows being slower than the latter, it's still cheaper.

> [!NOTE]
> If distributing software that needs to be compiled for all 3 systems, then it makes sense to use a `matrix` and run for all. 

---

## Scheduling
- **Avoid schedule workflows:** scheduling leads to stale unarchived repositories to be constantly wasting GitHub Actions usage. There's also no real benefit to testing and analyzing if nothing changed.
- **DependaBot scheduling:** DependaBot is an exception, as scheduling its checks is necessary to be able to use it. More on our guidelines for DependaBot [here](#dependabot).

---

## DependaBot
- **Schedule for either UTC, WET, WEST or `Europe/Lisbon` (or equivalent timezones, such as `Europe/London`).** If you want to secure the configuration, set it to a timezone that doesn't vary with DLS.
- **Schedule either early (06:00-07:00), in the evening (18:00-19:00) or late (22:00).**
- **Schedule according to project dimension.** If your project is considered big or pulls a lot of depencies, check on 3 days per week. If slightly smaller, only bother checking twice per week. If even smaller, check only once per week (preferable on Wednesday).

- > [!NOTE]
  > Good patterns are `MON,WED,FRI`, `TUE,THU` and `WED`. Avoid scheduling on weekends.
