.PHONY: all html pdf clean open serve

SRC = agent-skills.md
HTML = agent-skills.html
PDF = agent-skills.pdf

all: html pdf

html: $(HTML)

pdf: $(PDF)

$(HTML): $(SRC) inject-backdrop.js
	npx @marp-team/marp-cli --html $(SRC) -o $(HTML)
	node inject-backdrop.js $(HTML)

$(PDF): $(SRC)
	npx @marp-team/marp-cli --html $(SRC) -o $(PDF)

clean:
	rm -f $(HTML) $(PDF)

serve:
	python3 -m http.server 4005

open:
	(sleep 1 && open http://localhost:4005/$(HTML)) &
	@lsof -i :4005 >/dev/null 2>&1 || $(MAKE) serve
