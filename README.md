[Uploading index.ipynb…](){
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Phase 1 project "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "BUSINESS UNDERSTANDING\n",
    "Here we set the foundation of the project and the objectives are laid down. \n",
    "Our business problem is to find out what movies Microsoft can create and how they can have a breakthrough in the creation of movies.We will use data from box office collected from different locations to come up with relevant findings ,reasonable insights that aim to help the stakeholder work towards building a successful creative studio and deecide how to manouvre the creative studio world  "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "DATA UNDERSTANDING\n",
    "Data used for this project are movie datasets which are obtained from different locations with different file formats. This is relevant as the data currently available could hepl the stakeholder capture a few elements and gaps that could give them an edge was they embark on the creative studios ppath \n",
    "\n",
    "Exploring the datasets \n",
    "First off I'll import the relevant modules we will use 2 datasets for our project \n",
    "Then check the variables/columns in the data to get an overview of what the data contains"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 75,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "      id  release_date                                        movie  \\\n",
      "0      1  Dec 18, 2009                                       Avatar   \n",
      "1      2  May 20, 2011  Pirates of the Caribbean: On Stranger Tides   \n",
      "2      3   Jun 7, 2019                                 Dark Phoenix   \n",
      "3      4   May 1, 2015                      Avengers: Age of Ultron   \n",
      "4      5  Dec 15, 2017            Star Wars Ep. VIII: The Last Jedi   \n",
      "...   ..           ...                                          ...   \n",
      "5777  78  Dec 31, 2018                                       Red 11   \n",
      "5778  79   Apr 2, 1999                                    Following   \n",
      "5779  80  Jul 13, 2005                Return to the Land of Wonders   \n",
      "5780  81  Sep 29, 2015                         A Plague So Pleasant   \n",
      "5781  82   Aug 5, 2005                            My Date With Drew   \n",
      "\n",
      "     production_budget domestic_gross worldwide_gross  \n",
      "0         $425,000,000   $760,507,625  $2,776,345,279  \n",
      "1         $410,600,000   $241,063,875  $1,045,663,875  \n",
      "2         $350,000,000    $42,762,350    $149,762,350  \n",
      "3         $330,600,000   $459,005,868  $1,403,013,963  \n",
      "4         $317,000,000   $620,181,382  $1,316,721,747  \n",
      "...                ...            ...             ...  \n",
      "5777            $7,000             $0              $0  \n",
      "5778            $6,000        $48,482        $240,495  \n",
      "5779            $5,000         $1,338          $1,338  \n",
      "5780            $1,400             $0              $0  \n",
      "5781            $1,100       $181,041        $181,041  \n",
      "\n",
      "[5782 rows x 6 columns]\n"
     ]
    },
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>id</th>\n",
       "      <th>release_date</th>\n",
       "      <th>movie</th>\n",
       "      <th>production_budget</th>\n",
       "      <th>domestic_gross</th>\n",
       "      <th>worldwide_gross</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>Dec 18, 2009</td>\n",
       "      <td>Avatar</td>\n",
       "      <td>$425,000,000</td>\n",
       "      <td>$760,507,625</td>\n",
       "      <td>$2,776,345,279</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>May 20, 2011</td>\n",
       "      <td>Pirates of the Caribbean: On Stranger Tides</td>\n",
       "      <td>$410,600,000</td>\n",
       "      <td>$241,063,875</td>\n",
       "      <td>$1,045,663,875</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>Jun 7, 2019</td>\n",
       "      <td>Dark Phoenix</td>\n",
       "      <td>$350,000,000</td>\n",
       "      <td>$42,762,350</td>\n",
       "      <td>$149,762,350</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>May 1, 2015</td>\n",
       "      <td>Avengers: Age of Ultron</td>\n",
       "      <td>$330,600,000</td>\n",
       "      <td>$459,005,868</td>\n",
       "      <td>$1,403,013,963</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>Dec 15, 2017</td>\n",
       "      <td>Star Wars Ep. VIII: The Last Jedi</td>\n",
       "      <td>$317,000,000</td>\n",
       "      <td>$620,181,382</td>\n",
       "      <td>$1,316,721,747</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   id  release_date                                        movie  \\\n",
       "0   1  Dec 18, 2009                                       Avatar   \n",
       "1   2  May 20, 2011  Pirates of the Caribbean: On Stranger Tides   \n",
       "2   3   Jun 7, 2019                                 Dark Phoenix   \n",
       "3   4   May 1, 2015                      Avengers: Age of Ultron   \n",
       "4   5  Dec 15, 2017            Star Wars Ep. VIII: The Last Jedi   \n",
       "\n",
       "  production_budget domestic_gross worldwide_gross  \n",
       "0      $425,000,000   $760,507,625  $2,776,345,279  \n",
       "1      $410,600,000   $241,063,875  $1,045,663,875  \n",
       "2      $350,000,000    $42,762,350    $149,762,350  \n",
       "3      $330,600,000   $459,005,868  $1,403,013,963  \n",
       "4      $317,000,000   $620,181,382  $1,316,721,747  "
      ]
     },
     "execution_count": 75,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "import csv\n",
    "import pandas as pd\n",
    "\n",
    "data_1 = pd.read_csv('C:/Users/user/Desktop/DSC-PHASE 1 PROJECT/dsc-phase-1-project-v2-4/zippedData/tn.movie_budgets.csv/tn.movie_budgets.csv')\n",
    "\n",
    "df =pd.read_csv('C:/Users/user/Desktop/DSC-PHASE 1 PROJECT/dsc-phase-1-project-v2-4/zippedData/bom.movie_gross.csv/bom.movie_gross.csv')\n",
    "\n",
    "\n",
    "print(data_1)\n",
    "data_1.head(5)\n",
    "\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 76,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>title</th>\n",
       "      <th>studio</th>\n",
       "      <th>domestic_gross</th>\n",
       "      <th>foreign_gross</th>\n",
       "      <th>year</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Toy Story 3</td>\n",
       "      <td>BV</td>\n",
       "      <td>415000000.0</td>\n",
       "      <td>652000000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Alice in Wonderland (2010)</td>\n",
       "      <td>BV</td>\n",
       "      <td>334200000.0</td>\n",
       "      <td>691300000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>Harry Potter and the Deathly Hallows Part 1</td>\n",
       "      <td>WB</td>\n",
       "      <td>296000000.0</td>\n",
       "      <td>664300000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>Inception</td>\n",
       "      <td>WB</td>\n",
       "      <td>292600000.0</td>\n",
       "      <td>535700000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>Shrek Forever After</td>\n",
       "      <td>P/DW</td>\n",
       "      <td>238700000.0</td>\n",
       "      <td>513900000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5</th>\n",
       "      <td>The Twilight Saga: Eclipse</td>\n",
       "      <td>Sum.</td>\n",
       "      <td>300500000.0</td>\n",
       "      <td>398000000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>6</th>\n",
       "      <td>Iron Man 2</td>\n",
       "      <td>Par.</td>\n",
       "      <td>312400000.0</td>\n",
       "      <td>311500000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>7</th>\n",
       "      <td>Tangled</td>\n",
       "      <td>BV</td>\n",
       "      <td>200800000.0</td>\n",
       "      <td>391000000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>8</th>\n",
       "      <td>Despicable Me</td>\n",
       "      <td>Uni.</td>\n",
       "      <td>251500000.0</td>\n",
       "      <td>291600000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>9</th>\n",
       "      <td>How to Train Your Dragon</td>\n",
       "      <td>P/DW</td>\n",
       "      <td>217600000.0</td>\n",
       "      <td>277300000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10</th>\n",
       "      <td>Clash of the Titans (2010)</td>\n",
       "      <td>WB</td>\n",
       "      <td>163200000.0</td>\n",
       "      <td>330000000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11</th>\n",
       "      <td>The Chronicles of Narnia: The Voyage of the Da...</td>\n",
       "      <td>Fox</td>\n",
       "      <td>104400000.0</td>\n",
       "      <td>311300000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>12</th>\n",
       "      <td>The King's Speech</td>\n",
       "      <td>Wein.</td>\n",
       "      <td>135500000.0</td>\n",
       "      <td>275400000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>13</th>\n",
       "      <td>Tron Legacy</td>\n",
       "      <td>BV</td>\n",
       "      <td>172100000.0</td>\n",
       "      <td>228000000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>14</th>\n",
       "      <td>The Karate Kid</td>\n",
       "      <td>Sony</td>\n",
       "      <td>176600000.0</td>\n",
       "      <td>182500000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>15</th>\n",
       "      <td>Prince of Persia: The Sands of Time</td>\n",
       "      <td>BV</td>\n",
       "      <td>90800000.0</td>\n",
       "      <td>245600000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>16</th>\n",
       "      <td>Black Swan</td>\n",
       "      <td>FoxS</td>\n",
       "      <td>107000000.0</td>\n",
       "      <td>222400000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>17</th>\n",
       "      <td>Megamind</td>\n",
       "      <td>P/DW</td>\n",
       "      <td>148400000.0</td>\n",
       "      <td>173500000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>18</th>\n",
       "      <td>Robin Hood</td>\n",
       "      <td>Uni.</td>\n",
       "      <td>105300000.0</td>\n",
       "      <td>216400000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>19</th>\n",
       "      <td>The Last Airbender</td>\n",
       "      <td>Par.</td>\n",
       "      <td>131800000.0</td>\n",
       "      <td>187900000</td>\n",
       "      <td>2010</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                                                title studio  domestic_gross  \\\n",
       "0                                         Toy Story 3     BV     415000000.0   \n",
       "1                          Alice in Wonderland (2010)     BV     334200000.0   \n",
       "2         Harry Potter and the Deathly Hallows Part 1     WB     296000000.0   \n",
       "3                                           Inception     WB     292600000.0   \n",
       "4                                 Shrek Forever After   P/DW     238700000.0   \n",
       "5                          The Twilight Saga: Eclipse   Sum.     300500000.0   \n",
       "6                                          Iron Man 2   Par.     312400000.0   \n",
       "7                                             Tangled     BV     200800000.0   \n",
       "8                                       Despicable Me   Uni.     251500000.0   \n",
       "9                            How to Train Your Dragon   P/DW     217600000.0   \n",
       "10                         Clash of the Titans (2010)     WB     163200000.0   \n",
       "11  The Chronicles of Narnia: The Voyage of the Da...    Fox     104400000.0   \n",
       "12                                  The King's Speech  Wein.     135500000.0   \n",
       "13                                        Tron Legacy     BV     172100000.0   \n",
       "14                                     The Karate Kid   Sony     176600000.0   \n",
       "15                Prince of Persia: The Sands of Time     BV      90800000.0   \n",
       "16                                         Black Swan   FoxS     107000000.0   \n",
       "17                                           Megamind   P/DW     148400000.0   \n",
       "18                                         Robin Hood   Uni.     105300000.0   \n",
       "19                                 The Last Airbender   Par.     131800000.0   \n",
       "\n",
       "   foreign_gross  year  \n",
       "0      652000000  2010  \n",
       "1      691300000  2010  \n",
       "2      664300000  2010  \n",
       "3      535700000  2010  \n",
       "4      513900000  2010  \n",
       "5      398000000  2010  \n",
       "6      311500000  2010  \n",
       "7      391000000  2010  \n",
       "8      291600000  2010  \n",
       "9      277300000  2010  \n",
       "10     330000000  2010  \n",
       "11     311300000  2010  \n",
       "12     275400000  2010  \n",
       "13     228000000  2010  \n",
       "14     182500000  2010  \n",
       "15     245600000  2010  \n",
       "16     222400000  2010  \n",
       "17     173500000  2010  \n",
       "18     216400000  2010  \n",
       "19     187900000  2010  "
      ]
     },
     "execution_count": 76,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head(20)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 47,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>id</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>count</th>\n",
       "      <td>5782.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>mean</th>\n",
       "      <td>50.372363</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>std</th>\n",
       "      <td>28.821076</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>min</th>\n",
       "      <td>1.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>25%</th>\n",
       "      <td>25.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>50%</th>\n",
       "      <td>50.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>75%</th>\n",
       "      <td>75.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>max</th>\n",
       "      <td>100.000000</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                id\n",
       "count  5782.000000\n",
       "mean     50.372363\n",
       "std      28.821076\n",
       "min       1.000000\n",
       "25%      25.000000\n",
       "50%      50.000000\n",
       "75%      75.000000\n",
       "max     100.000000"
      ]
     },
     "execution_count": 47,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "data_1.describe()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "here we get a general information of the data like the mean and number of rows/movies next is to check for null values "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "RangeIndex: 5782 entries, 0 to 5781\n",
      "Data columns (total 6 columns):\n",
      " #   Column             Non-Null Count  Dtype \n",
      "---  ------             --------------  ----- \n",
      " 0   id                 5782 non-null   int64 \n",
      " 1   release_date       5782 non-null   object\n",
      " 2   movie              5782 non-null   object\n",
      " 3   production_budget  5782 non-null   object\n",
      " 4   domestic_gross     5782 non-null   object\n",
      " 5   worldwide_gross    5782 non-null   object\n",
      "dtypes: int64(1), object(5)\n",
      "memory usage: 271.2+ KB\n"
     ]
    }
   ],
   "source": [
    "data_1.info()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "From the information we observe there are no null values in our data_1 dataset\n",
    "The next line of code will confirm this"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 78,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "RangeIndex: 3387 entries, 0 to 3386\n",
      "Data columns (total 5 columns):\n",
      " #   Column          Non-Null Count  Dtype  \n",
      "---  ------          --------------  -----  \n",
      " 0   title           3387 non-null   object \n",
      " 1   studio          3382 non-null   object \n",
      " 2   domestic_gross  3359 non-null   float64\n",
      " 3   foreign_gross   2037 non-null   object \n",
      " 4   year            3387 non-null   int64  \n",
      "dtypes: float64(1), int64(1), object(3)\n",
      "memory usage: 132.4+ KB\n"
     ]
    }
   ],
   "source": [
    "df.info()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "In the df dataset for bm movies we have null entries in three columns/variables which ar studio, domestic_gross and foreign_gross this will need to be corrected for our visualization  \n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "DATA PERPARATION \n",
    "Here we basically do data cleaning in order to make our datasets more suitable for visualization we deal with outliers which may affect the data and handle the missing values,duplicates, null values and converting the variables into data formats that could be manipulated easily using visualization modules "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 48,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "id                   0\n",
       "release_date         0\n",
       "movie                0\n",
       "production_budget    0\n",
       "domestic_gross       0\n",
       "worldwide_gross      0\n",
       "dtype: int64"
      ]
     },
     "execution_count": 48,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "data_1.isna().sum()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 77,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "title                0\n",
       "studio               5\n",
       "domestic_gross      28\n",
       "foreign_gross     1350\n",
       "year                 0\n",
       "dtype: int64"
      ]
     },
     "execution_count": 77,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.isna().sum()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The code above gives us the number of missing values in the columns\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Now we remove the rows/movies with missing values"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 95,
   "metadata": {},
   "outputs": [],
   "source": [
    "df.dropna(inplace=True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 98,
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "Int64Index: 2007 entries, 0 to 3353\n",
      "Data columns (total 5 columns):\n",
      " #   Column          Non-Null Count  Dtype  \n",
      "---  ------          --------------  -----  \n",
      " 0   title           2007 non-null   object \n",
      " 1   studio          2007 non-null   object \n",
      " 2   domestic_gross  2007 non-null   float64\n",
      " 3   foreign_gross   2007 non-null   object \n",
      " 4   year            2007 non-null   int64  \n",
      "dtypes: float64(1), int64(1), object(3)\n",
      "memory usage: 94.1+ KB\n"
     ]
    }
   ],
   "source": [
    "df.info()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Now we try and identify duplicates in our data\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 94,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0       False\n",
       "1       False\n",
       "2       False\n",
       "3       False\n",
       "4       False\n",
       "        ...  \n",
       "3382    False\n",
       "3383    False\n",
       "3384    False\n",
       "3385    False\n",
       "3386    False\n",
       "Length: 3387, dtype: bool"
      ]
     },
     "execution_count": 94,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.duplicated(subset=['title'])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 49,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0       False\n",
       "1       False\n",
       "2       False\n",
       "3       False\n",
       "4       False\n",
       "        ...  \n",
       "5777    False\n",
       "5778    False\n",
       "5779    False\n",
       "5780    False\n",
       "5781    False\n",
       "Length: 5782, dtype: bool"
      ]
     },
     "execution_count": 49,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "data_1.duplicated(subset=['movie'])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 79,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0       False\n",
       "1       False\n",
       "2       False\n",
       "3       False\n",
       "4       False\n",
       "        ...  \n",
       "5777     True\n",
       "5778    False\n",
       "5779    False\n",
       "5780    False\n",
       "5781    False\n",
       "Length: 5782, dtype: bool"
      ]
     },
     "execution_count": 79,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "data_1.duplicated(subset=['production_budget'])\n",
    "\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "From checking the data we realize that there are many values in the columns production budget, domestic gross and worldwide gross that are zero and would interfere with our visualization we will need to get rid of them "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 88,
   "metadata": {},
   "outputs": [],
   "source": [
    "\n",
    "\n",
    "data_1['production_budget']=data_1['production_budget'].replace(\"[$,]\", \"\",regex=True).astype(int)\n",
    "data_1['production_budget'].apply(type)\n",
    "data_1['domestic_gross']=data_1['domestic_gross'].replace(\"[$,]\", \"\",regex=True).astype(int)\n",
    "data_1['domestic_gross'].apply(type)\n",
    "data_1['worldwide_gross']=data_1['worldwide_gross'].replace('[\\$,]','', regex=True).astype(float)\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Here the colmns domestic gross and production budget are converted to integer and worldwide gross to float since it had numbers too large to be converted to integer\n",
    "\n",
    " Next we remove the values with zero\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 73,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>id</th>\n",
       "      <th>release_date</th>\n",
       "      <th>movie</th>\n",
       "      <th>production_budget</th>\n",
       "      <th>domestic_gross</th>\n",
       "      <th>worldwide_gross</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>Dec 18, 2009</td>\n",
       "      <td>Avatar</td>\n",
       "      <td>425000000</td>\n",
       "      <td>760507625</td>\n",
       "      <td>2.776345e+09</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>2</td>\n",
       "      <td>May 20, 2011</td>\n",
       "      <td>Pirates of the Caribbean: On Stranger Tides</td>\n",
       "      <td>410600000</td>\n",
       "      <td>241063875</td>\n",
       "      <td>1.045664e+09</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>3</td>\n",
       "      <td>Jun 7, 2019</td>\n",
       "      <td>Dark Phoenix</td>\n",
       "      <td>350000000</td>\n",
       "      <td>42762350</td>\n",
       "      <td>1.497624e+08</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>4</td>\n",
       "      <td>May 1, 2015</td>\n",
       "      <td>Avengers: Age of Ultron</td>\n",
       "      <td>330600000</td>\n",
       "      <td>459005868</td>\n",
       "      <td>1.403014e+09</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>5</td>\n",
       "      <td>Dec 15, 2017</td>\n",
       "      <td>Star Wars Ep. VIII: The Last Jedi</td>\n",
       "      <td>317000000</td>\n",
       "      <td>620181382</td>\n",
       "      <td>1.316722e+09</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>...</th>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5775</th>\n",
       "      <td>76</td>\n",
       "      <td>May 26, 2006</td>\n",
       "      <td>Cavite</td>\n",
       "      <td>7000</td>\n",
       "      <td>70071</td>\n",
       "      <td>7.164400e+04</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5776</th>\n",
       "      <td>77</td>\n",
       "      <td>Dec 31, 2004</td>\n",
       "      <td>The Mongol King</td>\n",
       "      <td>7000</td>\n",
       "      <td>900</td>\n",
       "      <td>9.000000e+02</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5778</th>\n",
       "      <td>79</td>\n",
       "      <td>Apr 2, 1999</td>\n",
       "      <td>Following</td>\n",
       "      <td>6000</td>\n",
       "      <td>48482</td>\n",
       "      <td>2.404950e+05</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5779</th>\n",
       "      <td>80</td>\n",
       "      <td>Jul 13, 2005</td>\n",
       "      <td>Return to the Land of Wonders</td>\n",
       "      <td>5000</td>\n",
       "      <td>1338</td>\n",
       "      <td>1.338000e+03</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5781</th>\n",
       "      <td>82</td>\n",
       "      <td>Aug 5, 2005</td>\n",
       "      <td>My Date With Drew</td>\n",
       "      <td>1100</td>\n",
       "      <td>181041</td>\n",
       "      <td>1.810410e+05</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>5234 rows × 6 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "      id  release_date                                        movie  \\\n",
       "0      1  Dec 18, 2009                                       Avatar   \n",
       "1      2  May 20, 2011  Pirates of the Caribbean: On Stranger Tides   \n",
       "2      3   Jun 7, 2019                                 Dark Phoenix   \n",
       "3      4   May 1, 2015                      Avengers: Age of Ultron   \n",
       "4      5  Dec 15, 2017            Star Wars Ep. VIII: The Last Jedi   \n",
       "...   ..           ...                                          ...   \n",
       "5775  76  May 26, 2006                                       Cavite   \n",
       "5776  77  Dec 31, 2004                              The Mongol King   \n",
       "5778  79   Apr 2, 1999                                    Following   \n",
       "5779  80  Jul 13, 2005                Return to the Land of Wonders   \n",
       "5781  82   Aug 5, 2005                            My Date With Drew   \n",
       "\n",
       "      production_budget  domestic_gross  worldwide_gross  \n",
       "0             425000000       760507625     2.776345e+09  \n",
       "1             410600000       241063875     1.045664e+09  \n",
       "2             350000000        42762350     1.497624e+08  \n",
       "3             330600000       459005868     1.403014e+09  \n",
       "4             317000000       620181382     1.316722e+09  \n",
       "...                 ...             ...              ...  \n",
       "5775               7000           70071     7.164400e+04  \n",
       "5776               7000             900     9.000000e+02  \n",
       "5778               6000           48482     2.404950e+05  \n",
       "5779               5000            1338     1.338000e+03  \n",
       "5781               1100          181041     1.810410e+05  \n",
       "\n",
       "[5234 rows x 6 columns]"
      ]
     },
     "execution_count": 73,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "value_unwanted = 0.0\n",
    "data_1=data_1[(data_1['production_budget'] != value_unwanted) & (data_1['domestic_gross'] != value_unwanted) & (data_1['worldwide_gross'] != value_unwanted)]\n",
    "\n",
    "data_1"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "DATA ANALYSIS\n",
    "Here we handle some statistical properties of the columns/variables to further analyse the datasets"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 115,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>title</th>\n",
       "      <th>studio</th>\n",
       "      <th>domestic_gross</th>\n",
       "      <th>foreign_gross</th>\n",
       "      <th>year</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>'71</td>\n",
       "      <td>Uni.</td>\n",
       "      <td>1500000.0</td>\n",
       "      <td>1200000</td>\n",
       "      <td>2010.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>10 Cloverfield Lane</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>102 Not Out</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>11-11-11</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>12 Strong</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>...</th>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2002</th>\n",
       "      <td>Zoolander 2</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2003</th>\n",
       "      <td>Zootopia</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2004</th>\n",
       "      <td>[Rec] 2</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2005</th>\n",
       "      <td>mother!</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2006</th>\n",
       "      <td>xXx: The Return of Xander Cage</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>2007 rows × 5 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "                               title studio  domestic_gross foreign_gross  \\\n",
       "0                                '71   Uni.       1500000.0       1200000   \n",
       "1                10 Cloverfield Lane    NaN             NaN           NaN   \n",
       "2                        102 Not Out    NaN             NaN           NaN   \n",
       "3                           11-11-11    NaN             NaN           NaN   \n",
       "4                          12 Strong    NaN             NaN           NaN   \n",
       "...                              ...    ...             ...           ...   \n",
       "2002                     Zoolander 2    NaN             NaN           NaN   \n",
       "2003                        Zootopia    NaN             NaN           NaN   \n",
       "2004                         [Rec] 2    NaN             NaN           NaN   \n",
       "2005                         mother!    NaN             NaN           NaN   \n",
       "2006  xXx: The Return of Xander Cage    NaN             NaN           NaN   \n",
       "\n",
       "        year  \n",
       "0     2010.0  \n",
       "1        NaN  \n",
       "2        NaN  \n",
       "3        NaN  \n",
       "4        NaN  \n",
       "...      ...  \n",
       "2002     NaN  \n",
       "2003     NaN  \n",
       "2004     NaN  \n",
       "2005     NaN  \n",
       "2006     NaN  \n",
       "\n",
       "[2007 rows x 5 columns]"
      ]
     },
     "execution_count": 115,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.mode()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 114,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "domestic_gross    16700000.0\n",
       "year                  2013.0\n",
       "dtype: float64"
      ]
     },
     "execution_count": 114,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.median()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 51,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "31587757.0965064"
      ]
     },
     "execution_count": 51,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "data_1['production_budget'].mean()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 52,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "41873326.867001034"
      ]
     },
     "execution_count": 52,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "data_1['domestic_gross'].mean()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 90,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "425000000"
      ]
     },
     "execution_count": 90,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "data_1['production_budget'].max()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 91,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "1100"
      ]
     },
     "execution_count": 91,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "data_1['production_budget'].min()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Now we look at outliers "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 54,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0        True\n",
       "1        True\n",
       "2        True\n",
       "3        True\n",
       "4        True\n",
       "        ...  \n",
       "5777    False\n",
       "5778    False\n",
       "5779    False\n",
       "5780    False\n",
       "5781    False\n",
       "Name: production_budget, Length: 5782, dtype: bool"
      ]
     },
     "execution_count": 54,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "Q1 = data_1['production_budget'].quantile(0.25)\n",
    "Q3 = data_1['production_budget'].quantile(0.75)\n",
    "IQR = Q3 - Q1\n",
    "outliers = (data_1['production_budget'] < (Q1 - 1.5 * IQR)) | (data_1['production_budget'] > (Q3 + 1.5 * IQR))\n",
    "\n",
    "outliers\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "VISUALIZATION \n",
    "We will take undertake visualization that help us get insights on the creatives studio space that microsoft could consider when creating their own movies studio\n",
    "\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 61,
   "metadata": {},
   "outputs": [
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "c:\\Users\\user\\anaconda3\\envs\\learn-env\\lib\\site-packages\\seaborn\\_decorators.py:36: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.\n",
      "  warnings.warn(\n"
     ]
    },
    {
     "data": {
      "image/png": "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",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "import seaborn as sns\n",
    "x = data_1['movie'].head(3)\n",
    "y = data_1['production_budget'].head(3)\n",
    "\n",
    "ax= sns.barplot(x, y)\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "We will check if thers any correlation between the production_budget and worldwide_gross"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 72,
   "metadata": {},
   "outputs": [
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "c:\\Users\\user\\anaconda3\\envs\\learn-env\\lib\\site-packages\\seaborn\\_decorators.py:36: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.\n",
      "  warnings.warn(\n"
     ]
    },
    {
     "data": {
      "image/png": "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",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "x=data_1['production_budget'].head(1000)\n",
    "y=data_1['worldwide_gross'].head(1000)\n",
    "\n",
    "ax=sns.scatterplot(x,y)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "From the scatter plot we can infer that the two variables seem to be correlated somewhat. To confirm that we may need to plot a regression line\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 74,
   "metadata": {},
   "outputs": [
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "c:\\Users\\user\\anaconda3\\envs\\learn-env\\lib\\site-packages\\seaborn\\_decorators.py:36: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.\n",
      "  warnings.warn(\n"
     ]
    },
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='production_budget', ylabel='worldwide_gross'>"
      ]
     },
     "execution_count": 74,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data": {
      "image/png": "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",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {
      "needs_background": "light"
     },
     "output_type": "display_data"
    }
   ],
   "source": [
    "x=data_1['production_budget'].head(1000)\n",
    "y=data_1['worldwide_gross'].head(1000)\n",
    "\n",
    "sns.regplot(x,y)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "We see some correlation between the two variables but not really a causation effect which basically means that an increase in production budget does not necessarily cause the same or the opposite effect on the worldwide gross  "
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "learn-env",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.5"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}

