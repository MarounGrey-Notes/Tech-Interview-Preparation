# What's your testing methology?

✅ Comprehensive automated testing at unit, integration and UI level runs on every commit. We also do exploratory manual testing and usability studies.

❌ Testing is ad-hoc and relies on engineers manually verifying their own features before pushing to production. We should probably look into test automation...

# Do engineers own / control their production infrastructure? What happens if you discover a bug right after deployment?

✅ Engineers own the full stack including production. Post-deployment bugs get triaged based on user impact. Fixes follow release processes - no reckless hot fixes.

❌ Engineers have no production access and must file tickets for the Ops team to assess production bugs. Usually results in long delays before fixes or rollbacks can be attempted.

# How often are your engineers deliver a change into production? How quickly from identifying a bug, can the required change be in the customer's hands?

✅ Engineers ship multiple production updates per week ensuring rapid innovation. Bugs get fixed and deployed within 1 business day typically.

❌ Releases are monthly or quarterly massive headaches. Even show-stopping bugs take 3+ weeks to patch once layers of control processes slow things down.

# How much input do developers have on project design?

✅ Developer perspectives are key throughout the product design process - problem framing, solution options, validation testing etc. Design partnerships with engineering.

❌ The execs and sales teams design projects based on client asks. Engineering teams must then rapidly build out these product specs as dictated.

# How much time do you allow your engineers to develop their skills outside of deliverables?

✅ Skills growth is budgeted quarterly with 2 full weeks for things like professional courses, conferences, personal projects etc.

❌ Between client work, none really. Maybe watch some YouTube videos or Pluralsight on weekends if motivated enough.

# Who get's called when software breaks at 3am? Why?

✅ No one! Alerts wake up the on-call support rotation. Only life-critical services page developers personally in extreme cases (basically never).

❌ Engineers carry 24/7 support pagers. Management has always subscribed to the "you build it, you support it at any cost" philosophy when it comes to outages and customer issues.

# (for medium and big companies on site) Given new machine, can new engineer download, build and run all code in less then 30 mins? If not, what's stopping them?

✅ Yes definitely! Our developer onboarding results in all repositories, keys and tools being setup for engineers from day one through automation.

❌ No way. Our monolithic decade-old codebase has so many deeply rooted dependencies, proprietary toolchains and tangled configurations that literally no one fully understands or has the ability to untangle. Good luck!
