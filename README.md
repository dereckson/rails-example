Rails Sample App on OpenShift
=========================

Quickstart Rails application for OpenShift.

Running on OpenShift
--------------------

Create an account at http://openshift.redhat.com/

Create a rails application:

    rhc create-app -a railsapp -t rack-1.1

Add MySQL support to your application:

    rhc add-cartridge -a railsapp -c mysql-5.1

Add this upstream Rails quickstart repo:

    cd railsapp
    git remote add upstream -m master git://github.com/gshipley/rails-openshift-quickstart.git
    git pull -s recursive -X <theirs upstream master>

Then push the repo upstream:

    git push

That's it, you can now check your application at:

    http://railsapp-<your namespace>.rhcloud.com
