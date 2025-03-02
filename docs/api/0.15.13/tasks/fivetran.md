---
sidebarDepth: 2
editLink: false
---
# Fivetran Tasks

::: tip Verified by Prefect
<div class="verified-task">
<svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 48 48" fill="none">
<circle cx="24" cy="24" r="24" fill="#42b983"/>
<circle cx="24" cy="24" r="9" stroke="#fff" stroke-width="2"/>
<path d="M19 24L22.4375 27L29 20.5" stroke="#fff" stroke-width="2"/>
</svg>
<div>
These tasks have been tested and verified by Prefect.
</div>
</div>
:::

---

This module contains a task for starting and monitoring [Fivetran](https://fivetran.com/) connector sync jobs
 ## FivetranSyncTask
 <div class='class-sig' id='prefect-tasks-fivetran-fivetran-fivetransynctask'><p class="prefect-sig">class </p><p class="prefect-class">prefect.tasks.fivetran.fivetran.FivetranSyncTask</p>(connector_id=None, **kwargs)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/fivetran/fivetran.py#L11">[source]</a></span></div>

Task for running Fivetran connector sync jobs.

This task assumes the user is a Fivetran user (https://fivetran.com) who has successfully setup a connector and has access to the API credentials for that user (https://fivetran.com/account/settings, "API Config").

**Args**:     <ul class="args"><li class="args">`connector_id (str, optional)`: Default connector id to use for sync jobs, if none is         specified to `run`.     </li><li class="args">`**kwargs (Any, optional)`: additional kwargs to pass to the base Task constructor</li></ul>

|methods: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:----|
 | <div class='method-sig' id='prefect-tasks-fivetran-fivetran-fivetransynctask-run'><p class="prefect-class">prefect.tasks.fivetran.fivetran.FivetranSyncTask.run</p>(api_key, api_secret, connector_id=None, poll_status_every_n_seconds=15, manual=True)<span class="source"><a href="https://github.com/PrefectHQ/prefect/blob/master/src/prefect/tasks/fivetran/fivetran.py#L31">[source]</a></span></div>
<p class="methods">Task run method for Fivetran connector syncs.<br><br>An invocation of `run` will attempt to start a sync job for the specified `connector_id`. `run` will poll Fivetran for connector status, and will only complete when the sync has completed or when it receives an error status code from an API call.<br><br>**Args**:     <ul class="args"><li class="args">`api_key (str)`: `API key` per https://fivetran.com/account/settings; should be secret!     </li><li class="args">`api_secret (str)`: `API secret` per https://fivetran.com/account/settings; should be secret!     </li><li class="args">`connector_id (str, optional)`: if provided, will overwrite value provided at init.     </li><li class="args">`poll_status_every_n_seconds (int, optional)`: this task polls the Fivetran API for status,         if provided this value will override the default polling time of 15 seconds.     </li><li class="args">`manual (bool, optional)`: if provided, will overwrite Prefect's changes         to the Fivetran connector's schedule, keeping it on Fivetran auto scheduling</li></ul> **Returns**:     <ul class="args"><li class="args">`dict`: connector_id (str) and succeeded_at (timestamp str)</li></ul></p>|

---
<br>


<p class="auto-gen">This documentation was auto-generated from commit <a href='https://github.com/PrefectHQ/prefect/commit/n/a'>n/a</a> </br>on February 23, 2022 at 19:26 UTC</p>