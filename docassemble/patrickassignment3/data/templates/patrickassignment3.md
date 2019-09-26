**Memo**


**To:** ${ user.name.first } ${ user.name.last }  

 
**From:** Patrick White  

 
**Date:** ${ format_date(today()) }  

 
% if eligible:
You have indicated that you are eligible for Legal Aid. Your lawyer has already received your Legal Aid certificate. A member of our staff will be able to assist you in the next steps you need to take to set up an account.
% else:
You have indicated that you are not eligible for Legal Aid. Don’t worry! Our firm has reasonable rates for on-going matters as well as limited scope retainers for simple matters. A member of our staff will provide you with further information about these two options.
% endif
 
% if len(household) == 0:
You indicated that you live alone.

% elif len(household) == 1:
You indicated that you live with the following person:

${ household }  

% else:
You indicated that you live with the following people:

${ household } 

% endif

Please print this document, sign it and return it to our office with **9 days** 
(${ format_date( current_datetime() + date_interval(days=9), format='M/d/yyyy' ) }).