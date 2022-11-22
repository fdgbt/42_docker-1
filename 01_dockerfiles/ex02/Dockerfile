FROM ruby

# CONFIG CONTAINER
RUN apt-get update && apt-get install nodejs -y && gem install rails

# Copy rails application
ONBUILD ADD /app /opt/app

# Set working directory
WORKDIR /opt/app

# Install the DataBase
ONBUILD RUN bundle install && rake db:migrate && rake db:setup && rake db:seed
