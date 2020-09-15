#!/usr/bin/python3

import os, sys

def check():
	print('\033[31mchecking')
	print("CWD: " + os.getcwd())
	print("Script: " + sys.argv[0])
	print(".EXE: " + os.path.dirname(sys.executable))
	print("Script dir: " + os.path.realpath(os.path.dirname(sys.argv[0])))
	pathname, scriptname = os.path.split(sys.argv[0])
	print("Relative script dir: "+pathname)
	print("Script dir: "+ os.path.abspath(pathname))
	print('\033[0m')

def getDirectory():
	return os.getcwd()
	# tmp=sys.argv[0].split('/')
	# tmp = os.getcwd()
	# dir=tmp
	# for i in range(len(tmp)-1):
	# 	dir=dir+tmp[i]+'/'
	# return dir

root = getDirectory()
ext = '.py'

print('counter is running in ', root)

if len(sys.argv) > 2:
	root=sys.argv[2]
	ext=sys.argv[1]

if len(sys.argv) > 1:
	ext=sys.argv[1]

print('given directory', root)
print('given file extension:', ext)

def countLines(filePath):
	with open(filePath) as fp:
		line = fp.readline()
		cnt = 1
		while line:
			line = fp.readline()
			cnt += 1
		print('   total lines: \033[1;34;38m{}\033[0m'.format(cnt))
		print('')
		return cnt

sum=0
for path, subdirs, files in os.walk(root):
	for name in files:
		filePath=os.path.join(path, name)
		fileName=name
		if ext in fileName:
			print('\033[1;33;33m', fileName, '\033[0m', 'in directory\033[1;33;33m', path, '\033[0m')
			print('-->')
			sum=sum+countLines(filePath)

print('total number of \033[1;31;33m', ext, '\033[0m code is:\033[0m \033[1;31;33m', sum, '\033[0m')
