# MSE Seminar Data Base Systems Spring 17 on Triple Stores
This is the repository for the MSE Seminar Data Base Systems Spring 2017 on "Evaluating Open Source Triple Stores with Massive Data from the example of Virtuoso Universal DB Server, Apache Jena TDB and RDFLib/PostgreSQL DB".


## Postgres with rdflib as reference
To compare your individual triple store system with postgres we prepared a setup with postgres and rdflib.
 
### Setup
  1. Install Postgres 9.6 and create a database called "benchmark" (I recommend to use the the docker container from https://hub.docker.com/_/postgres/)
  2. Install Python 3.6 and pip 3
  3. Clone this repository ``git clone https://github.com/geometalab/MSE-Database-Seminar-Triple-Stores.git``
  4. Switch to the bsbmtools-0.2 directory and generate the sample data ``./generate -fc -pc 10000 -ud -fn scale10000 -s ttl`` 
  5. Move the scale10000.ttl file into the rdflib directory and edit the config.ini for the setup
  6. Install the project requirements with pip3 ``pip3 install -r requirements.txt``
  7. To import the data into the postgres database run the store_data.py (this could take awhile) ``python3 store_data.py``
  8. Now you could run the queries ``python3 query_data.py``

### Queries
For the benchmark we implement the following queries:  
http://wifo5-03.informatik.uni-mannheim.de/bizer/berlinsparqlbenchmark/spec/ExploreUseCase/index.html  

As you can see in the folder rdflib there is a queries.py file with the queries from the benchmark with filled random variables.
(rdflib doesn't support DESCRIBE so the query number 8 is not possible)  
Your goal is now to implement the same queries with your specific framework and compare them with the postgres rdflib setup.
