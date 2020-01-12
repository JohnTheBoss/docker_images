FROM sharelatex/sharelatex

RUN wget http://mirror.ctan.org/systems/texlive/tlnet/update-tlmgr-latest.sh && sh update-tlmgr-latest.sh
RUN tlmgr option repository https://ctan.net/systems/texlive/tlnet 
RUN tlmgr install scheme-full
