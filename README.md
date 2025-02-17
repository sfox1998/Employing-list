require 'composure'

module CensusHelper
  extend Composure

  @name = ""
  @other_names = ["Chris Donkor", "Chelsea Gram", "Ben Hammond", "Micheal Kealy"]

  command:set_name do |name|
    @name = name
    puts "Name set to: #{@name}"
  end

  command:add_name do |name|
    @other_names << name
    puts "Added #{name} to the list."
  end

  command:list_names do
    puts "Other names in the list:"
    @other_names.each_with_index { |name, index| puts "#{index + 1}. #{name}" }
  end

  command:schedule_fingerprint do |location, date, time|
    if @name.empty?
      puts "Please set your name first using the 'set_name' command."
    else
      # Code to interact with a scheduling API or website
      puts "Fingerprint appointment for #{@name} scheduled for #{date} at #{time} in #{location}."
    end
  end

  command:document_checklist do
    if @name.empty?
      puts "Please set your name first using the 'set_name' command."
    else
      puts "Document checklist for #{@name}:"
      puts "- Employment Confirmation email with barcode (electronic or printed)"
      puts "- Two forms of original identity proofing documents (one with photo)"
    end
  end

  command:portal_forms do
    puts "Forms to complete in the Applicant Portal:"
    puts "- CD-415, Emergency Contact Information"
    puts "- D-999, Overtime Policy Agreement"
    puts "- D-168, New Employee Data"
    puts "- D-1199, Payment Authorization"
    puts "- D-186F, Census Employment Agreement"
    puts "- D-1129, Personal Telephone Reimbursement Policy Agreement"
    puts "Applicant Portal: https://recruitment.2020census.gov/ats/careersite/census.aspx?site=1&c=census"
  end

  command:contact_info do
    puts "Contact Information:"
    puts "- General inquiries: 1-855-562-2020 (Press option 3, then enter your Zip Code)"
  end
end
# Census Employment Onboarding CLI Tool

This command-line interface (CLI) tool helps new Census employees navigate the onboarding process.

## Commands

* `set_name [name]`: Sets the name of the hired person.
* `add_name [name]`: Adds a new name to the list of other names.
* `list_names`: Displays the list of other names.
* `schedule_fingerprint [location] [date] [time]`: Schedules a fingerprint appointment. Requires the hired person's name to be set first.
* `document_checklist`: Displays a checklist of required documents for Fingerprint Day. Requires the hired person's name to be set first.
* `portal_forms`: Lists the forms to be completed in the Applicant Portal.
* `contact_info`: Provides contact information for general inquiries.

## Example Usage
