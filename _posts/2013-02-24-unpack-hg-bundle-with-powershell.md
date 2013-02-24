--- 
layout: post 
title: Unpack HG bundle with PowerShell
category: misc
tags: powershell,hg
--- 
Recently I needed to strip three HG changesets, that had not yet left 
my local repo, but wanted to extract some of the code within those
changesets for something I needed. As I'm sure I would find myself 
needing this again, I figured I would archive it here for myself. 

The Mercurial Wiki discusses how to [manually unpack a changeset bundle 
created by hg strip](http://mercurial.selenic.com/wiki/ManuallyUnpackingStripBundle). 
It even gives a simple code example on how to unpack the bundle using 
python. The `hg strip` command produces bundles that are compressed 
with BZip2. The PowerShell version of this is quite simple, however 
there is no native BZip2 support in PowerShell so I left that portion 
to the all trusty [7-Zip](http://7-zip.org).

	# Read the compressessed bundle in, reading all at once
	# versus line-by-line (i.e. ReadCount set to 0)
	$bundle = ".\.hg\strip-backup\551b9da1b6ed-backup.hg"
	$hgBzip = Get-Content -ReadCount 0 -Encoding Byte -Path $bundle

	# Strip the 6 byte header off the front, put back the 2 byte 'BZ' and save to temp file.
	$bzOutFile = Join-Path ([System.IO.Path]::GetTempPath()) "$((get-item $bundle).BaseName).bz2"
	$bzHeader = [System.Text.Encoding]::ASCII.GetBytes("BZ")
	$bzHeader + ($hgBzip | select -Last ($hgBzip.Length - 6)) | Set-Content -Encoding Byte $bzOutFile
	
	# Uncompress using 7Z to current directory (change output dir with -o switch)
	7z.exe x $bzOutFile
	rm $bzOutFile

