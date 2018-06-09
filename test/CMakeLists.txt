
function(cat_example exec srcs)
	add_executable(${exec} ${srcs})
	target_link_libraries(${exec} PRIVATE cat Threads::Threads)
	target_include_directories(${exec} PRIVATE inc)
	target_compile_options(${exec} PRIVATE "-O0;-Wall;-Wextra")
endfunction()


cat_example(test-container test/container.cpp)
cat_example(test-traits test/traits.cpp)
cat_example(test-match test/match.cpp)
cat_example(test-infix test/infix.cpp)
cat_example(test-section test/section.cpp)
cat_example(test-tuple test/tuple.cpp)
cat_example(test-functional test/functional.cpp)
cat_example(test-iterator test/iterator.cpp)
cat_example(test-optional test/optional.cpp)
cat_example(test-forward test/forward.cpp)
cat_example(test-string_view test/string_view.cpp)

cat_example(test-functor test/functor.cpp)
cat_example(test-bifunctor test/bifunctor.cpp)
cat_example(test-monoid test/monoid.cpp)
cat_example(test-applicative test/applicative.cpp)
cat_example(test-monad test/monad.cpp)
cat_example(test-foldable test/foldable.cpp)

cat_example(test-show test/show.cpp)
cat_example(test-pretty test/pretty.cpp)
cat_example(test-read test/read.cpp)

cat_example(test-bits_type test/bits_type.cpp)
cat_example(test-forall test/forall.cpp)
