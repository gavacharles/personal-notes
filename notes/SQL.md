# SQL

**Summary**: Notes on SQL databases and query engines, including spatial SQL in DuckDB and PostGIS.
**Last updated**: 2026-11-18

---

- [Optimizing DuckDB Spatial Queries (Geomermaids)](https://www.geomermaids.com/cookbook/duckdb-spatial/): Translates PostGIS spatial joins to DuckDB, with EXPLAIN plans and timings. Covers RTREE indexes, one spatial predicate per join, missing KNN, and inlining literals plus sorting GeoParquet for big speedups. See [[Data]]. `duckdb` `postgis` `spatial-join` `rtree` `geoparquet` `query-optimization`
