Table Creates and Drops Log
======

This is coming soon.

Some thoughts: 

1. Does it make sense to swap time from unix time so that people can understand it or leave as is to help investigating? Leaning towards readability as job_id is included and can be used for investigation.

2. There can be a lot of tables created/dropped in a short time range. What makes some more notable than others? How can we filter the list so that it is more actionable/useful?