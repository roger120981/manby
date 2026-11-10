The changes in each version of manby, from the titles of the pull requests that made them.

## [0.1.5](https://github.com/roger120981/manby/compare/v0.1.4...v0.1.5) - 2026-11-10

### Added

- Read GeoParquet and Arrow, and tile DuckDB queries and data frames from Python ([#13](https://github.com/birkskyum/manby/pull/13))

### Fixed

- Read GeoJSON with a third coordinate in linear time ([#11](https://github.com/birkskyum/manby/pull/11))

### Changed

- Manby 0.1.4, on PyPI and with binaries for macOS and Linux
- Manby 0.1.3
- --no-simplification-of-shared-nodes in a third of the memory, and no panic on collapsed lines ([#3](https://github.com/birkskyum/manby/pull/3))
- Manby 0.1.2
- --as-needed-per-tile, which fits each tile on its own rather than its whole zoom level
- Manby 0.1.1, manby-wagyu 0.5.1
- Rustfmt
- A simple ring's union without the sweep
- Thanks to Erica Fischer, who created tippecanoe
- Tippecanoe-rs in the workspace, and every crate ready for crates.io
- Bring in tippecanoe-rs, the faithful port, with its history
- No colon before the list
- Manby's polygon cleaning, and the water polygons' new time
- Keep a ring's bottom point while it is the only point there
- REPLAY_THREADS
- Pass over hot pixel rows with nothing within the edge's x range
- Index large rings by y when placing rings in the tree
- Relabel only the absorbed ring's points when joining rings
- Take bounds off the front of a deque, not a vector
- Clean polygons with manby's own copy of wagyu
- The other formats' speed as two-step pipelines
- Other formats by way of GDAL, not terrio in particular
- A Why manby? page, and other formats by way of terrio
- A landing page of its own, and VitePress's colors throughout
- The chart and the tables say which data each benchmark tiles
- The chart shows the seven benchmarks on Linux
- Manby first in the benchmark chart
- A landing page with the benchmark, and documentation, for GitHub Pages
- Numbers from the Yoga for Linux, and manby's memory work
- Under a memory budget, big tiles may take three quarters of it
- :shrink_to_fit leaves storage in the file as it is
- MANBY_ONLY runs only manby, against the reference's tilesets of an earlier run
- A read chunk lets go of its hash tables and growing room
- A kept feature takes 88 bytes instead of 120
- A level's spools go when the level whose inputs they hold is done
- Queued tiles wait as a few numbers, and become tasks when they start
- A tile's memory estimate counts the features it keeps while it is made
- The cluster attributes are made where they are read
- PAUSE before each run, as in large.sh
- The C++ tippecanoe as the reference, on macOS and on Linux
- Tippecanoe's arm64 builds and fused multiply-add; how the coordinator waits
- PAUSE before each run, for the machine to cool down
- The coordinator waits awake before sleeping; helpers are woken one per part
- Run.sh reports peak memory and medians; Linux times in seconds; OUT for the tilesets
- Manby decode, enumerate, overzoom and json-tool: tippecanoe's other programs
- README and DESIGN: manby join, its benchmarks, and how it orders shared tiles
- Manby join: tile-stats take numbers as they are, and values sort by a prefix first
- Manby join reads TIPPECANOE_MAX_THREADS, as tile-join does
- Manby join: keys of tiles that share a z/x/y worked out ahead, on all threads
- Manby join: tile-stats leave out values past a full list without searching it
- Manby join: overzooming without tippecanoe-rs's hash tables
- Manby join against tile-join
- Biggest tiles first in manby join; spilled PMTiles data read back by two threads
- Manby join: only zlib's and libdeflate's streams of an unchanged tile pass through
- Manby join: tiles read from a mapping per batch, and unchanged tiles keep their compression
- Under tile-join's name, tile-join's usage message, without manby's options
- Manby join: tippecanoe's tile-join, making the same tiles
- Tests that set tippecanoe-rs's tile-stats limit take turns
- Name the program on the first line of their complaints, as tippecanoe does
- Real directories at every depth, so no recipe writes into tippecanoe-rs
- Large-input numbers after the store changes
- Benchmark numbers after the clustering work, and the points-cluster benchmark
- Accumulated numbers in 16 bytes, and kept features' short lists at one
- Tiles with the most data run together within 768 MB, not 1 GB
- A pass merges its tiles' layer statistics as they come in
- Points-cluster, clustering within 10 pixels with a summed attribute
- Feature ids in a column of their own
- Value ends in 4 bytes, with the points where they pass 4 GB
- Child inputs go to the spool in their parts; reads reserve geometry room
- Features in 64 bytes; extents and label points in columns of their own
- Candidates keep their gaps apart, and only where a tile needs them
- Test that a clustering run tippecanoe-rs panics on fails cleanly
- Ingest frees each chunk's tables and features once they are merged
- Concatenation does not read the accumulated value as a number
- A tile task that panics fails the run instead of hanging it
- Jemalloc keeps freed address space mapped
- Lay the store out in feature order always; guess the chunk of a position
- Accumulate attributes as numbers until the tile's features are chosen
- Final benchmark numbers with peak memory
- --memory-budget and the large-input results
- Root reads take their vertex counts from the split; bench/large.sh
- Past the budget, lay the store out in feature order
- Group interned values by shard when merging, not as they are interned
- FxHash for the MVT encoder's dedup maps
- Merge main into work/memory
- Past the budget, ingest, store and tile data go to a file
- A vector whose storage may be a temporary file
- Tiles that fit the size limit whatever zlib makes are compressed with libdeflate, skipping zlib; --compression=zlib keeps zlib for every tile
- Pack read candidate geometry in a fixed bit width
- Smaller PMTiles sink buffers and a 16 MB tile memory budget
- Zlib's deflateBound for tippecanoe's settings, tested against zlib's own; example comparing zlib -6 with libdeflate levels on archive tiles
- Merge branch 'work/memory'
- Jemalloc with few arenas and immediate purging; merged features written in place and sorted in place
- 24-byte candidates, lazily allocated attribute vectors in kept features, one tag vector per encoded layer
- Reads split by vertices, spools read only their own buffer, PMTiles finish reads spilled tiles instead of mapping them
- Store geometry as delta varints, moved into the store unchopped; tiles keep only what later passes need
- Candidate geometry in 12 bytes a vertex; ingest: parsed input pages released
- Store and tiler: smaller records and tables, waiting data in large blocks, persistent helper threads
- MapLibre Tiles output
- MLT web profile: tiles every MapLibre GL JS with MLT reads, with numbers for integers
- Merge main into work/memory
- Compact tile inputs, each tile read and made in one task, waiting tile data in temporary files
- Describe MLT output in DESIGN.md
- Test MLT output: the sinks, the option, and the encoder against mlt-core's reader
- Make test-golden-mlt: the golden tests as MVT and MLT, compared tile by tile
- Read MVT tiles for MLT without mlt-core's decode limit, and check against mlt-core's reader
- Write MapLibre Tiles with --tile-format=mlt, behind the mlt cargo feature
- Add a README with the benchmark results
- Variable depth pyramids (-at)
- Merge work/ingest into work/tiler
- Keep what -at needs from tippecanoe's temporary files
- Keep four tasks per thread queued, no MvtLayer tables without a postfilter, helper threads only for heavy layers
- No global counters or environment reads; timing and tracing are TileOptions; compress with crate::compress; lib.rs takes the tiling options from TileOptions::new
- Tiler tests: prefilter and postfilter against tippecanoe-rs, layer counts included
- --prefilter and --postfilter, run on every attempt as tippecanoe does; remove the filter and shared border tests from the golden skip list
- Drop the reference test's check for unread input formats
- --detect-shared-borders
- TileOptions::new builds the tiling options from Options, Plan and the store
- Read Geobuf input
- Fix the replay example for Feature.ix; parallel per-feature cleaning with dynamic scheduling and no geometry copies in the selection loop
- Clippy
- Test that a whole run makes the same tileset with 1, 3 and 18 threads
- Phases example: use mimalloc as the command does
- Read CSV and FlatGeobuf input, and run the CSV, FlatGeobuf, layer, parallel and radix recipes in test-golden
- Pipelined zoom levels with priority scheduling, a faster exact encoder, and reuse of results that a pass would repeat
- Determinism test for reading, clippy cleanups, and the new Feature.ix in the tiler's test
- Make test-golden: tippecanoe's .json.check recipes with manby, with a skip list
- :run: open the sink, read, order, tile and write the metadata; shared nodes for -pn
- Size each PMTiles data piece exactly
- Tippecanoe's sort, zoom and drop rate guessing, and minimum zooms
- Name the compressor type in the compression benchmark
- Options parsing and parallel GeoJSON reading that matches tippecanoe-rs's
- Add a compression benchmark and notes on other cloud-native outputs
- Spill PMTiles tile data in batches per shard
- Build PMTiles directories and write tile data in parallel, with the same bytes
- Tile in memory with tippecanoe's selection and retries, checked against tippecanoe-rs
- Write tile files from a few writer threads, and add a sink benchmark
- Write PMTiles, MBTiles and tile directories directly, matching tippecanoe-rs
- Compress tiles with a reused zlib or libdeflate state per thread
- Start manby: design, skeleton and benchmarks
- Clean up after the port: no lint allowances, a README
- Merge branch 'port/json2geobuf'
- Run the geobuf tests with the Rust json2geobuf
- Port json2geobuf from the geobuf npm package as an example
- Check the storage dump only on macOS, where its expected values come from
- Use try_decode in overzoom, and add tests with values from the C++
- Clean up clippy findings in the pipeline modules
- Clear PROGRESS_TIME_ENABLED in decode and tile-join
- Replace the program files instead of overwriting them, which macOS kills
- Build the programs before the golden tests run
- Build the programs before the golden tests run
- Wrap scaled-up coordinates to 40 bits like the C++ draw bitfield
- Port main.cpp and geobuf.cpp, and honor PROGRESS_TIME_ENABLED in progress_time
- Port main.cpp (work in progress)
- Write json-tool output from the input bytes of strings
- Add a switch for the programs whose progress_time always returns false
- Write the child shards through one compressor per file, as the C++ does
- Use try_decode, perror_io and SQLite's own open error message
- Exit like the C++ when thread_create fails
- Tidy tile.rs declarations
- Port usage.cpp
- Format the getopt tests
- Add unit tests for tile.rs and plugin.rs
- Keep the raw bytes of metadata strings read from metadata.json and PMTiles
- Port read_json.cpp
- Port getopt_long from glibc
- Clean up clippy warnings in tile.rs
- Test tile directories and PMTiles output and input against the C++
- Port evaluator.cpp
- Port tile.cpp and plugin.cpp (first draft)
- Port tile-join.cpp and tile-cache.hpp
- Port jsontool.cpp
- Port overzoom.cpp
- Port enumerate.cpp
- Port decode.cpp
- Port attribute.cpp
- Note that wagyu matches the C++ built without floating point contraction
- Port memfile, pool, sort, compression, serial, and the GeoJSON, CSV and FlatGeobuf readers
- Port csv.cpp
- Port write_json.cpp
- Port geojson-loop.cpp
- Port mvt.cpp
- Port the parts of protozero that mvt.cpp and geobuf.cpp use
- Port jsonpull
- Note that clipper2 matches the C++ built without floating point contraction
- Port geometry.cpp, clip.cpp, visvalingam.cpp and shared_borders.cpp
- Test mbtiles tiles, tilestats and metadata against the C++
- Test pmtiles against values from the C++ pmtiles.hpp
- Use perror_io from cstd in dirtiles
- Port pmtiles_file.cpp
- Port dirtiles.cpp
- Port mbtiles.cpp
- Port pmtiles/pmtiles.hpp
- Port projection.cpp
- Port text.cpp
- Port the C library helpers in cstd.rs
- Port milo/dtoa_milo.h
- Add the skeleton: shared types, module stubs and the test Makefile
- Add porting notes
- Start the Rust port of tippecanoe with the C++ test fixtures

### Dependencies

- Bump rusqlite from 0.40.2 to 0.41.1 ([#6](https://github.com/birkskyum/manby/pull/6))
- Bump the cargo group with 2 updates ([#5](https://github.com/birkskyum/manby/pull/5))
- Bump tikv-jemallocator from 0.6.1 to 0.7.0 ([#7](https://github.com/birkskyum/manby/pull/7))

## [0.1.4](https://github.com/birkskyum/manby/compare/v0.1.3...v0.1.4) - 2026-11-07

### Added

- `pip install manby` and `uvx manby`, from wheels on PyPI for macOS and Linux
- Binaries for macOS and Linux on the GitHub releases, which write MapLibre Tiles too

## [0.1.3](https://github.com/birkskyum/manby/compare/v0.1.2...v0.1.3) - 2026-11-07

### Fixed

- `--no-simplification-of-shared-nodes` in a third of the memory, and no panic on lines that collapse to one point ([#3](https://github.com/birkskyum/manby/pull/3))

## [0.1.2](https://github.com/birkskyum/manby/compare/v0.1.1...v0.1.2) - 2026-11-06

### Added

- `--as-needed-per-tile`, which fits each tile on its own rather than its whole zoom level

## [0.1.1](https://github.com/birkskyum/manby/compare/v0.1.0...v0.1.1) - 2026-11-06

### Faster or smaller

- The union of a simple polygon ring without wagyu's sweep, 5 to 9% less CPU on the census tracts

## [0.1.0](https://github.com/birkskyum/manby/releases/tag/v0.1.0) - 2026-11-05

The first release.
