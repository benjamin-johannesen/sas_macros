### empirical_cdf

**Version 0.1.0**

First version of empirical_cdf macro that calculates the empirical cumulative distribution function for a variable.

### calculate_sd

**Version 0.1.0**

First version of calculate_sd macro that calculates standardized differences (SD) of variables between two groups.

### hash_match

Matching using a hash-table merge approach

**Version 0.3.3**

- Hotfix of edge-case bug introduced in version 0.3.2

**Version 0.3.2**

- Matching with "mixed" replacement can now be done using replace = m, see documentation.

- Macro parameter "inexact_vars" added to macro, to make it possible to manually specify
the exact variables used in "match_inexact" in cases where the macro incorrectly
identifies too many.

- The limit_tries parameter has been renamed to max_tries and the underlying way the 
macro sets the maximum number of tries to find controls have been slightly modified to
make it less convoluted. 

**Version 0.3.1**

- Fixed a bug where the macro would fail in certain scenarios if no potential controls exists.


**Version 0.3.0**

- Inexact matching can now be done using the match_inexact parameter. 

- Extensive changes to how the macro work to make the match_inexact parameter
a natural part of using the macro. 

- Overhaul of used terminology. Hopefully it is now more clear how the macro works.

- Made a new set of examples that highlight the flexibility of the match_inexact 
parameter, but also highlight that mistakes can easily be made that are not
necessarily easy to see.


**Version 0.2.1**

- Minor language and code revisions.

- Macro parameter "print_notes" can now be used to toggle whether or not notes are 
printed in the log. By default notes are now disabled. 

- Added a verbose macro parameter that can be used to make the macro print what 
is happening during macro execution to the log. This is primarily thought to be 
useful during development and debugging, but it might also help the interested
user to understand what is happening in the macro during execution.

- Added macro parameter keep_add_vars, making it possible to specify variables from
the input dataset that should be included in the output data that is not already
automatically included.

- Added a __match_date variable to the output, to make it more intuitive and
explicit what the matching date is.
  
  
**Version 0.2.0**

Further development of the macro. 

**Version 0.1.0**

First initial attempt at making macro using a hash-table merge to do matching.
Should work as intended, but should be used with caution.



### mask_table

Masks/suppresses/censors a table of aggregated counts, if the table contains
counts that are deemed person-sensitive.

**Version 0.1.1**

Refined how masking of large counts are done. 

**Version 0.1.0**

First attempt of generalized implementation of masking algorithm. So far the 
macro expects input data with the same structure as the output from the pt_char 
macro. Default macro parameters are set to facilitate the use of this macro in 
connection with the pt_char macro, but if the table data if not output from 
pt_char it might still be easy to modify it so that it can be used with the
macro. See examples. 


### ps_match

Efficient propensity score pair matching using a hash-table merge.

**Version 0.1.3**

- It is now possible to specify the match ID variable name in the output using the match_id_name parameter.

- Default values have been added to out_pf (_ps_match), group_var(group), and ps_var(ps) to facilitate use of macro.

- A jitter_ps parameter has been added that can be used to control whether or not small amounts of random noise is added to the ps values. This is done by default to ensure that random matches are made in scenarios where there are multiple persons with the same ps. This is important if the ps only takes discrete values, but this can now be disabled if the user does not want this behavior.


**Version 0.1.2**

- Fixed bug causing matching without replacement (replace = n) to not work as intended.


### pt_char

Produces a so-called "table 1" with aggregated patient characteristics

**Version 0.2.1**

- Fixed a bug where the macro would fail if both the strata and the weight
  macro parameters were used.
  
- Included a few more tests.

**Version 0.2.0**

- Changed version numbering to reflect that the macro is still under active
  development and most changes will likely not be backwards-compatible.
  This change will hopefully not cause too much confusion. Few people (if any) 
  are using the macro at this point.
  
- Extensive renaming of macro parameters to (hopefully) make the macro more
  intuitive to understand and use.
  
- Added a macro parameter controlling whether or not percentage signs are 
  included for percentage statistics in the output.
  
- Added a where-condition.

- Fixed a bug, where if a variable was included in more than one of var_list,
  strata, and by, the macro would break down.
  
- It is now possible to choose what statistics to calculate for each separate
  variable in var_list using the var_stats macro parameter.
  
