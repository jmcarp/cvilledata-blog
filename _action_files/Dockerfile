FROM fastai/jekyll:latest

WORKDIR /fastpages
COPY . .
RUN chmod u+x action_entrypoint.sh
RUN chmod u+x word2post.sh
RUN dos2unix /fastpages/*.sh

# Hack: Work around breaking changes in nbconvert 6.x
RUN pip install git+https://github.com/jmcarp/nbdev.git@nbconvert-5.x-compat
RUN pip install 'nbconvert<6.0'

CMD [ "/fastpages/action_entrypoint.sh" ]
