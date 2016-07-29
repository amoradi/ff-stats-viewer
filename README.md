# FF Stats Viewer

The purpose of this app is to view fantasy football stats in a manner where users can view data in a way which facilitates reasoning with the data. Views can be *composed* based on simple URL routing patterns. 

## Views

### Positional View

User can view single or multiple postion stats as averages or sums in a single table.

#### URL Routing Pattern

	// scoring - "standard", "ppr", "half-ppr"
	// stats - "sum", "avg"
	// years back - 0, 1, 2, 3, 4...data conditioned
	// positions - "d", "k", "qb", "rb", "te", "wr"

	/ scoring / stats / years back / position(s)

- /standard/sum/1/qb - retrieves QB stats from last year
- /ppr/avg/5/rb-wr - retrieves WR average stats from 2011-2015
- /ppr/sum/5/rb-te-wr - retrieves year 2011 RB, TE & WR stats
- /half-ppr/avg/0/te-wr - retrieves this year's stats (sum not averaged) for TE's and WR's
- /half-ppr/avg/1/te-wr - retrieves last year's stats (sum not averaged) for TE's and WR's

### Player View

Individual player stats (averages or sums) in a single table.

#### URL Routing Pattern

	/ position / stats / years back / fistname-lastname

- /wr/sum/2/dez-bryant - show 2014 stats for dez bryant
- /wr/avg/3/dez-bryant - shows average stats from 2013-2015 for dez bryant 

### Player Comparison View

Multiple player stats viewed in multiple tables. 1 player per table.

#### URL Routing Pattern

	/ compare / [position / stats / years back / fistname-lastname /], [position / stats / years back / fistname-lastname /] ...

- /compare/wr/sum/2/dez-bryant/wr/sum/2/aj-green - compare 2014 dez bryant & aj green stats (2 tables)
- /compare/wr/avg/3/dez-bryant/rb/sum/2/carlos-hyde - compare average stats from 2013-2015 for dez bryant with Carlos Hyde's 2014 stats (2 tables)
