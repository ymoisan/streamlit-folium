# CKSFO : User Tasks Level of Detail Typology

Based on [this gist](https://gist.github.com/josher19/749343).

`C` : Cloud level = Too abstract

`K` : Kite level = Activities = long term goal with no precise ending. Perform several functional tasks in the context of an activity

`S` : Sea Level = Functional tasks = reasonably expect to complete in a single sitting

`F` : Fish level = Sub-functional tasks = Small tasks that by themselves don’t mean much.  I’ll do several of these before I reach a functional level goal.

`O` : Ocean floor level = too detailed

# C`KS`FO User stories / tasks
There really is just one `K` story here : get interaction between Folium and Streamlit (ST) elements.  Specific (`S`) examples include the following items.

## Synchronize feature list

As a Streamlit User, I want to fill an ST dropdown (or other) control(s) using information from a select query done in the Folium Window (iframe or not), so that I can select from that list of features in the ST control.

**Option 1 : live sync**

A user could zoom/pan in the map to their heart's content without any ST control being updated.  Users could even select features without ST controls updating.  Only when the user is satisfied with their selection can they click a "Synchronize" button that would likely go through some data mangling function to extract e.g. filename or file url from the [JSON/dict] returned from the Folium selection and update the ST control with that information.

**Option 2 : live sync**

Alternatively, users may want the content of a ST control to be continuously updated upon actions in the map.  All features in the current viewport could be fed into the control at all times.  Selecting features in Folium would act as a filter on the set of features visible.

# Technical considerations

The current version of Streamlit-Folium uses a static Streamlit component.  Is there a need for a true bi-directional control, given the fact that the map will be used to update ST, but not the other way around.  Could we add a return value to the current Folium.Map ?
