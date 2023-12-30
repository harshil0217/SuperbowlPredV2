import datetime

regular_season_timeframes = {
  2002: [datetime.date(2002, 9, 5), datetime.date(2003, 1, 5)],
  2003: [datetime.date(2003, 9, 4), datetime.date(2004, 1, 4)],
  2004: [datetime.date(2004, 9, 9), datetime.date(2005, 1, 2)],
  2005: [datetime.date(2005, 9, 8), datetime.date(2006, 1, 1)],
  2006: [datetime.date(2006, 9, 7), datetime.date(2007, 1, 1)],
  2007: [datetime.date(2007, 9, 6), datetime.date(2007, 12, 30)],
  2008: [datetime.date(2008, 9, 4), datetime.date(2008, 12, 28)],
  2009: [datetime.date(2009, 9, 10), datetime.date(2010, 1, 3)],
  2010: [datetime.date(2010, 9, 9), datetime.date(2011, 1, 2)],
  2011: [datetime.date(2011, 9, 8), datetime.date(2012, 1, 1)],
  2012: [datetime.date(2012, 9, 5), datetime.date(2012, 12, 30)],
  2013: [datetime.date(2013, 9, 5), datetime.date(2013, 12, 29)],
  2014: [datetime.date(2014, 9, 4), datetime.date(2014, 12, 28)],
  2015: [datetime.date(2015, 9, 10), datetime.date(2016, 1, 3)],
  2016: [datetime.date(2016, 9, 8), datetime.date(2017, 1, 1)],
  2017: [datetime.date(2017, 9, 7), datetime.date(2017, 12, 31)],
  2018: [datetime.date(2018, 9, 6), datetime.date(2018, 12, 30)],
  2019: [datetime.date(2019, 9, 5), datetime.date(2019, 12, 29)],
  2020: [datetime.date(2020, 9, 10), datetime.date(2021, 1, 3)],
  2021: [datetime.date(2021, 9, 9), datetime.date(2022, 1, 9)],
  2022: [datetime.date(2022, 9, 8), datetime.date(2023, 1, 8)]
}

season_timeframes = {
  2002: [datetime.date(2002, 9, 5), datetime.date(2003, 1, 26)], 
  2003: [datetime.date(2003, 9, 4), datetime.date(2004, 2, 1)],
  2004: [datetime.date(2004, 9, 9), datetime.date(2005, 2, 6)],
  2005: [datetime.date(2005, 9, 8), datetime.date(2006, 2, 5)],
  2006: [datetime.date(2006, 9, 7), datetime.date(2007, 2, 4)],
  2007: [datetime.date(2007, 9, 6), datetime.date(2008, 2, 3)],
  2008: [datetime.date(2008, 9, 4), datetime.date(2009, 2, 1)],
  2009: [datetime.date(2009, 9, 10), datetime.date(2010, 2, 7)],
  2010: [datetime.date(2010, 9, 9), datetime.date(2011, 2, 6)],
  2011: [datetime.date(2011, 9, 8), datetime.date(2012, 2, 5)],
  2012: [datetime.date(2012, 9, 5), datetime.date(2013, 2, 3)],
  2013: [datetime.date(2013, 9, 5), datetime.date(2014, 2, 2)],
  2014: [datetime.date(2014, 9, 4), datetime.date(2015, 2, 1)],
  2015: [datetime.date(2015, 9, 10), datetime.date(2016, 2, 7)],
  2016: [datetime.date(2016, 9, 8), datetime.date(2017, 2, 5)],
  2017: [datetime.date(2017, 9, 7), datetime.date(2018, 2, 4)],
  2018: [datetime.date(2018, 9, 6), datetime.date(2019, 2, 3)],
  2019: [datetime.date(2019, 9, 5), datetime.date(2020, 2, 2)],
  2020: [datetime.date(2020, 9, 10), datetime.date(2021, 2, 7)],
  2021: [datetime.date(2021, 9, 9), datetime.date(2022, 2, 13)],
  2022: [datetime.date(2022, 9, 8), datetime.date(2023, 2, 12)]
}

team_map = {
  'Lions': 'Detroit Lions',
  'Falcons': 'Atlanta Falcons',
  'Ravens': 'Baltimore Ravens',
  'Bills': 'Buffalo Bills',
  'Panthers': 'Carolina Panthers',
  'Bears': 'Chicago Bears',
  'Bengals': 'Cincinnati Bengals',
  'Browns': 'Cleveland Browns',
  'Cowboys': 'Dallas Cowboys',
  'Cardinals': 'Arizona Cardinals',
  'Broncos': 'Denver Broncos',
  'Packers': 'Green Bay Packers',
  'Texans': 'Houston Texans',
  'Colts': 'Indianapolis Colts',
  'Jaguars': 'Jacksonville Jaguars',
  'Chiefs': 'Kansas City Chiefs',
  'Rams': 'Los Angeles Rams',
  'Chargers': 'Los Angeles Chargers',
  'Raiders': 'Las Vegas Raiders',
  'Dolphins': 'Miami Dolphins',
  'Vikings': 'Minnesota Vikings',
  'Patriots': 'New England Patriots',
  'Saints': 'New Orleans Saints',
  'Giants': 'New York Giants',
  'Jets': 'New York Jets',
  'Eagles': 'Philadelphia Eagles',
  'Steelers': 'Pittsburgh Steelers',
  'Seahawks': 'Seattle Seahawks',
  '49ers': 'San Francisco 49ers',
  'Buccaneers': 'Tampa Bay Buccaneers',
  'Titans': 'Tennessee Titans',
  'Commanders': 'Washington Commanders'
}


def postseason_helper(x, date_col):
    """Check if date is in regular season or postseason
    
    Args:
        x (row): Row from a dataframe
        date_col (str): Column name containing the date
                
    Returns:
        bool: True if date is in postseason, False if in regular season
            
    """
    date = x[date_col]
    season = 0
    for key, value in season_timeframes.items():
        if value[0] <= date.date() <= value[1]:
            season = key
            break
    dates = regular_season_timeframes[season]
    if dates[0] <= date.date() <= dates[1]:
        return True
    return False
        
    


# +
def filter_out_postseason(data, date_col):
    """Filter dataframe to only regular season data
    
    Args:
        data (dataframe): Dataframe containing date_col
        date_col (str): Column name containing the date
        
    Returns: 
        Filtered dataframe containing only regular season data
        
    """
    keep = data.apply(lambda x: postseason_helper(x, date_col), axis = 1)
    data = data[keep]
    return data

def date_helper(x, date_col):
    """Converts date to season year
    
    Args:
        x (row): Row from a dataframe
        date_col (str): Column containing date 
        
    Returns:
        Row with date value converted to season year (e.g. 2022)
        
    """
    date = x[date_col]
    for key, value in regular_season_timeframes.items():
        if value[0] <= date.date() <= value[1]:
            date = key
            break
    x[date_col] = date
    return x


def simplify_date(data, date_col):
    """Converts dates in dataframe to season years
    
    Args:
        data (dataframe): Dataframe containing date_col
        date_col (str): Column name with date values
        
    Returns: 
        Dataframe with date values converted to season years 
        
    """
    data = data.apply(lambda x: date_helper(x, date_col), axis = 1)
    return data

def opp_wins_helper(x, date_col, opp_col, team_wins):
    date = x[date_col]
    opp = x[opp_col]
    wins = team_wins[date][opp]
    return wins

def generate_opponent_wins(data, date_col, opp_col, team_wins):
    opp_wins = data.apply(lambda x: opp_wins_helper(x, date_col, opp_col, team_wins), axis = 1)
    data["opponent wins"] = opp_wins
    return data


    