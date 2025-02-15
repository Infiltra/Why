# Why
Notes
cmake invocation

cmake -DCMAKE_C_COMPILER=/usr/local/bin/afl-clang-fast -DCMAKE_CXX_COMPILER=/usr/local/bin/afl-clang-fast++ -DCMAKE_BUILD_TYPE=Debug -Dsse2=OFF -DCMAKE_INSTALL_PREFIX=/home/neverville/XERCES/xerces-c-3.3.0 ../

before make
SANs needed
export AFL_USE_ASAN=1
export AFL_USE_MSAN=1 --> Only ASAN used in this run
export AFL_USE_UBSAN=1

-- Xerces-C++ configuration summary
-- --------------------------------
-- 
--   Version:                   3.3.0
--   Library interface version: 3.3
-- 
--   Installation directory:    /home/neverville/XERCES/xerces-c-3.3.0
--   C compiler:                /usr/local/bin/afl-clang-fast
--   C++ compiler:              /usr/local/bin/afl-clang-fast++
-- 
--   Build shared libraries:    ON
--   Path delimiters:           "/"
--   File Manager:              POSIX
--   Mutex Manager:             standard
--   Transcoder:                icu
--   NetAccessor:               curl
--   Message Loader:            inmemory
--   XMLCh type:                char16_t
-- Configuring done
-- Generating done
-- Build files have been written to: /home/neverville/XERCES/xerces-c-3.3.0/build


AFL map size set in cmin to
Setting AFL_MAP_SIZE=154610


afl-fuzz -L 0 -T all -M master -i input_unique/ -o output/ -m none -t 50000 -P explore -- xerces-c-3.3.0/build/tests/XSerializerTest @@

 afl-fuzz -L 0 -T all -S 0 -i input_unique/ -o output/ -m none -t 50000 -P crash -- xerces-c-3.3.0/build/tests/XSerializerTest @@
 
 afl-fuzz -L 0 -T all -S 1 -i input_unique/ -o output/ -m none -t 50000 -P crash -- xerces-c-3.3.0/build/tests/XSerializerTest @@
 
 afl-fuzz -L 0 -T all -S 2 -i input_unique/ -o output/ -m none -t 50000 -P explore -- xerces-c-3.3.0/build/tests/XSerializerTest @@


