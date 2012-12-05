# TODOs
* DONE change fancy printf stuffs done in exp-plan to `column -t`
* DONE exp-results
    * run restriction
    * condition restrcition
    * Consider using sqlite or relying on some relational store w/ SQL, i.e., don't be too fancy with the selection
* DONE exp-results bug fix for empty args
* DONE exp-results query on measurements (=/</>/<=/>=)
* DONE exp-plan with the output of exp-results query (e.g., when you want to rerun exps for certain conditions with failures/anomalies/etc.)
* `exp measure` for running newly added measures: requires partial assembly for exp.measure, and separating the running part from exp-run.
* exp-rerun for re-running past runs: do a copy --archive --link from the run dir and simply run it again?
* better hardlinking: first create a copy if necessary in .exp/ and hardlink that one so that user can modify anything outside run/ without worrying about overwriting all the snapshots.
* keep links to currently running batch and/or run
* better messaging: let exp.sh dup terminal fds, so all msg can still reach the term

## GUI
* DONE chasis with express.js + node + bootstrap + coffee-script
* DONE workflow design

* DONE specifying the conditions of interest for planning and listing results
* tabulating results
    * DONE basic table
    * DONE w/ or w/o aggregation: avg, med, sum, min, max, ...
        * DONE choose aggregation function for each measurements
        * DONE aggregated values popup
    * DONE show all records if aggregation for run# is turned off
    * DONE number formatting
    * DONE numeric type cell align right
    * DONE different number precision for diff measurements (using mean of |fractional|s of the actual values)
    * DONE fill empty results for selected conditions
        * from the popup, let user easily add exp plans
    * show multiple aggregation for each measurements
* DONE clean up navbar with scrollspy
* Encapsulate with CoffeeScript classes
* easy creating/removing of condition values
* d3 plots of results
    * bar chart
    * scatter plot
    * small multiple
* list of runs and batches
    * planning/altering a batch (mostly just ordering)
* batch page
    * monitoring running state
    * start/stop/resume
* run page
    * monitoring logs
    * better looking run summary page

* Title with .exp/description
* DONE add right margin to icons in h2 instead of space

## Wild ideas
* temporal trends in runs
* approximation/prediction of measurements, i.e., measures without actual runs
* estimating time for a plan based on other runs: will need to keep track of
  wallclock time etc.
* concise way to specify parallel execution order in the plan

<!--
vim:undofile
map <D-CR>  <C-\><C-N>:!make -C ~/2012/Projects/ExpKit install PREFIX=~<CR>:!cd ~/2012/Study/Giraph-vs-Socialite/graph-benchmarks; exp gui stop; exp gui start &<CR>
-->