# Why
Notes
cmake invocation
cmake -DCMAKE_C_COMPILER=/usr/local/bin/afl-clang-fast -DCMAKE_CXX_COMPILER=/usr/local/bin/afl-clang-fast++ -DCMAKE_BUILD_TYPE=Debug -Dsse2=OFF -DCMAKE_INSTALL_PREFIX=/home//XERCES/xerces-c-3.3.0 ../


-- Xerces-C++ configuration summary
-- --------------------------------
-- 
--   Version:                   3.3.0
--   Library interface version: 3.3
-- 
--   Installation directory:    /home//XERCES/xerces-c-3.3.0
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
-- Build files have been written to: /home//XERCES/xerces-c-3.3.0/build
