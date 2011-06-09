Clockwork is a cron replacement. It runs as a lightweight, long-running Ruby 
process which sits alongside your web processes (Mongrel/Thin) and your 
worker processes (DJ/Resque/Minion/Stalker) to schedule recurring work at 
particular times or dates. For example, refreshing feeds on an hourly basis,
or send reminder emails on a nightly basis, or generating invoices once a
month on the 1st.

https://github.com/adamwiggins/clockwork