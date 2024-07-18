# Feature Engineering # 1
**OVERVIEW**

This project will highlight Feature Engineering skills and techniques for categorical and continuous features in an ML workflow environment for data preprocessing.

**PROCESS**

I started by reading in the two data sets that came with the data file; a training and testing set with the testing set missing a price column. The data set describes plane flights and routes. I then did a quick top-level feature analysis of the data to understand feature structures, data types, and missing values (which were removed since there was only a single record with missing values). The two data sets were then concatenated so the cleaning could be applied to both datasets simultaneously. Lastly, some general cleaning was conducted to transform all text characters to lowercase characters

There were nine categorical features that we deconstructed and/or encoded:

**airline** - _indigo_

**date_of_journey** - _24/03/2019_

**source** - _banglor_

**destination** - _new delhi_

**route** - _ccu -> nag -> blr_

**dep_time** - _22:20_

**arrival_time** - _1:10 22 mar_

**duration** - _2h 50m_

**total_stops** -_ 2 stops_

**additional_info** - _in flight meal not included_

Features associated with datetime were deconstructed to have each individual associated unit be represented by their own unique feature. Each original feature had to be split into unique characters such as '/', ':', or ' '. Once all the text characters were removed, the new features datatype was then transformed into an integer. The outcome led to three new features associated with date to replace 'date_of_journey': day, month, and year. The 'duration' feature was deconstructed into 'total_duration_by_min'. Lastly, both 'dep_time' and 'arrival_time' were both deconstructed with respect to hour and minute features.


Features associated with locations were broken up and or given unique key values. There were six new features from the deconstruction of 'route': 

start, stop_1, stop_2, stop_3, stop_4, and stop_5

All of these features were then encoded using the same dictionary of values ensuring that a location would not be encoded twice. The same technique was then executed for the source and destination.

With 'total_stops' not being associated with any other feature in this data set, a simple numeric encoding process was initiated.

Finally with the categorical features 'airline' and 'additional_info' having a large quantity of categories, a simple onehot encode was implemented on the two creating a new binary feature for all the levels.
