
# Changelog

## v3.0.0

With this major release, the entire API has been rethought to allow the picker to be much more configurable and extensible. These are the most notable updates:

- [#20]({%= gitrepo_url %}/issues/20): Introduced a new [time picker]({%= pkg.homepage %}/time.htm).
- [#112]({%= gitrepo_url %}/issues/112): Firefox select month/year fix.
- [#84]({%= gitrepo_url %}/issues/84): Scrollbar not hidden to avoid page shift.
- [#89]({%= gitrepo_url %}/issues/89): Better event handling on clicks/focuses/keydowns within the holder.
- [#98]({%= gitrepo_url %}/issues/98): Destroy picker data from element.
- Added Grunt.js build system.
- Added QUnit test suite.
- Added Travis integration.
- Updated themes to be Sass-based.
- Removed “Inline” theme.
- Removed jam.js bindings within `package.json`.

To enable all this goodness, some **backward-incompatible changes** have been introduced. These are the main ones:

<a name="zero-as-index"></a>
- [#85]({%= gitrepo_url %}/issues/85): Months have __zero-as-index__:

	Just as in JavaScript’s native Date object, the `month` used to create dates is now 	based on zero as the first index. Meaning:

	```
	[2013,0,1] → January 01, 2013
	[2013,11,1] → December 01, 2013
	```

- API revised:

	```
	isOpen → get('open')
	getDate → get('select')
	getDateLimit → get('min') or get('max')
	setDate → set('select', …)
	setDateLimit → set('min', …) or set('max', …)
	show → set('view', …)
	```

- Options revised:

	```
	showMonthsFull → showMonthsShort
	showWeekdaysShort → showWeekdaysFull
	yearSelector → selectYears
	monthSelector → selectMonths
	dateMin → min
	dateMax → max
	datesDisabled → disable
	onSelect → onSet
	```

- Options removed:

	```
	monthPrev
	monthNext
	```
	To add labels for the month navigation tabs, use CSS pseudo-elements instead.

- A few [HTML classes]({%= pkg.homepage %}/date.htm#classes) name and property changes.

- [Formatting rules]({%= pkg.homepage %}/date.htm#formats) that appear within a word need to be escaped with an exclamation mark (!).


<br>
#### Please do read the [docs]({%= pkg.homepage %}/date.htm#options) and [api]({%= pkg.homepage %}/api.htm) to see exactly how these new options and methods work.




<br>
## Older changelogs

If you’re looking for changes in older versions, please [browse the tags]({%= ___.gitrepo_url %}/tags) for the relevant commit archive and changelog file.


