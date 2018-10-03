Smart Referer
=============
This extension automatically hides the referer when changing domains.

The domain changing is based on the same origin policy.

Options
-------
* *Strict Mode*: When enabled, *Smart Referer* will treat different subdomains
  as being different websites. Therefore `a.example.com` and `b.example.com`
  will not be able to see each other's referer. In general this often causes
  issues and results in little to no privacy improvement, we therefore highly
  recommended leaving this disabled.

* *Exceptions*: A list of different source and destination hosts that should
  never have their referer changed. For instance a rule with Source `*` and
  Destination `*.example.com` will pass referers of all websites to any resource
  served at `example.com` (including its subdomains).

* *Whitelist Sources*: An list of documents containing additional whitelist
  rules. The [default whitelist](https://raw.githubusercontent.com/meh/smart-referer/gh-pages/whitelist.full.txt)
  tries to minimize the impact of this extension on everyday web surfing while
  still providing the maximum referer privacy possible under these
  circumstances. [This may not be what you want](https://github.com/meh/smart-referer/issues/50).
  
  Misbehaviour in the face of spoofed referers is also not that common anymore,
  so most users should not experience any issues by disabling this feature
  entirely.
  
* *Rewrite Mode*: Can be used to change what is sent to the server instead of
  the original referer header. The default (*Send the URL you're going to as
  referer*) is known to cause the least issues on most sites and is therefore
  recommended.

A website is not working, what should I do?
-------------------------------------------
If a website is not working properly the first thing you can try is making sure
strict mode is disabled.

If the issue isn't solved, you can try adding an exeception for the domain by
adding the source `*.<domain.name>` and the destination `*`. Allowing
`www.example.com` to access everything with the orignal referer you would
therefore add `*.example.com` as the source and `*` as the destination.

If you want to help finding a reasonable whitelist entry that solves the issue
for everyone, [please see this Wiki entry](https://github.com/meh/smart-referer/wiki/Gathering-Data-for-Whitelist-Entries)
on how to gather additional information and finding reasonable/minimal rules.

**Please** also [open an issue about it](https://github.com/meh/smart-referer/issues/new)
(even if you cannot find a solution) and we'll try to add the proper patterns to the
autoupdated whitelist.

Want to help out?
-----------------
Please that a look at the many features proposed in our bug tracker tagged as
[„Help wanted“](https://github.com/meh/smart-referer/issues?q=is%3Aissue+is%3Aopen+label%3A%22Help+wanted%22).
Most of these would be nice to have in *Smart Referer* but are unlikely to be
added by the core team.

Also don't be shy to ask questions in the bug tracker!
