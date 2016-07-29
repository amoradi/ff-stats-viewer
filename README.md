# FF Stats Viewer

The purpose of this app is to view fantasy football stats in a manner where users can view data in a way which facilitates reasoning with the data. Views can be *composed* based on simple URL routing patterns. 

## Stats

### Positional Stats

User can view single or multiple postion stats as averages or sums in a single table.

#### URL Routing Pattern

	// scoring - "std", "ppr", "half-ppr"
	// stats - "sum", "avg"
	// years back - 0, 1, 2, 3, 4...data conditioned
	// positions - "d", "k", "qb", "rb", "te", "wr"

	/ scoring / stats / years back / position(s)

- /std/sum/1/qb - retrieves QB stats from last year
- /ppr/avg/5/rb-wr - retrieves WR average stats from 2011-2015
- /ppr/sum/5/rb-te-wr - retrieves year 2011 RB, TE & WR stats
- /half-ppr/avg/0/te-wr - retrieves this year's stats (sum not averaged) for TE's and WR's
- /half-ppr/avg/1/te-wr - retrieves last year's stats (sum not averaged) for TE's and WR's

### Player Stats

Individual player stats (averages or sums) in a single table.

#### URL Routing Pattern

	// years back - all (displays each year seperately), 0, 1, 2, 3, 4...data conditioned 

	/ position / scoring / stats / years back / firstname-lastname

- /wr/ppr/sum/2/dez-bryant - show 2014 stats for Dez Bryant
- /wr/std/avg/3/dez-bryant - shows average stats from 2013-2015 for Dez Bryant
- /wr/std/sum/all/dez-bryant - shows all yearly stats for Dez Bryant 


### Player Comparison Stats

Multiple player stats viewed in multiple tables. 1 player per table.

#### URL Routing Pattern

	/ compare / [position / scoring / stats / years back / firstname-lastname /], [position / scoring /stats / years back / firstname-lastname /] ...

- /compare/wr/ppr/sum/2/dez-bryant/wr/half-ppr/sum/2/aj-green - compare 2014 Dez Bryant & AJ Green stats (2 tables)
- /compare/wr/std/avg/3/dez-bryant/rb/ppr/sum/2/carlos-hyde - compare average stats from 2013-2015 for Dez Bryant with Carlos Hyde's 2014 stats (2 tables)
