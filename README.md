编译动态库

gcc -o libdiff.so -fPIC -shared bsdiff.c

gcc -o libpatch.so -fPIC -shared bspatch.c

编译测试文件

gcc -o testdiff testdiff.c ./libdiff.so

gcc -o testpatch testpatch.c ./libpatch.so

测试

./testdiff mbpkg_old.txt mbpkg_new.txt mbpkg_recov.diff

./testpatch mbpkg_old.txt mbpkg_patch.txt mbpkg_recov.diff

python

python gen_diff_patch.py mbpkg_old.txt mbpkg_new.txt mbpkg_recov_py.diff

./testpatch mbpkg_old.txt mbpkg_patch_py.txt mbpkg_recov_py.diff
