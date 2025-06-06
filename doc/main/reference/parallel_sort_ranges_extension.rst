.. _parallel_sort_ranges_extension:

parallel_sort ranges interface extension
========================================

.. contents::
    :local:
    :depth: 1

Description
***********

|full_name| implementation extends the `oneapi::tbb::parallel_sort specification <https://oneapi-spec.uxlfoundation.org/specifications/oneapi/latest/elements/onetbb/source/algorithms/functions/parallel_sort_func>`_
with overloads that takes the container by forwarding reference.


API
***

Header
------

.. code:: cpp

    #include <oneapi/tbb/parallel_sort.h>

Syntax
------

.. code:: cpp

    namespace oneapi {
        namespace tbb {

            template <typename Container>
            void parallel_sort( Container&& c );
            template <typename Container, typename Compare>
            void parallel_sort( Container&& c, const Compare& comp );

        } // namespace tbb
    } // namespace oneapi

Functions
---------

.. cpp:function:: template <typename Container> void parallel_sort( Container&& c );

    Equivalent to ``parallel_sort( std::begin(c), std::end(c), comp )``, where `comp` uses `operator<` to determine relative orderings.

.. cpp:function:: template <typename Container, typename Compare> void parallel_sort( Container&& c, const Compare& comp );

    Equivalent to ``parallel_sort( std::begin(c), std::end(c), comp )``.

Example
-------

This interface may be used for sorting rvalue or constant views:

.. literalinclude:: ./examples/parallel_sort_ranges_extension_example.cpp
    :language: c++
    :start-after: /*begin_parallel_sort_ranges_extension_example*/
    :end-before: /*end_parallel_sort_ranges_extension_example*/
