sync/stylindex:
	rsync -ua stylindex/stylindex-web-remote/ ../stylindex/stylindex-web/ --delete --exclude-from 'exclude.txt'

r-sync/stylindex:
	rsync -ua ../stylindex/stylindex-web/ stylindex/stylindex-web-remote/ --delete --exclude-from 'exclude.txt'

.PHONY: sync/stylindex