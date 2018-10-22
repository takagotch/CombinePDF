### CombinePDF
---
https://smallpdf.com/merge-pdf

https://combinepdf.com/ja/

https://github.com/boazsegev/combine_pdf

```
gem install combine_pdf

```

```ruby
pdf = CombinePDF.new
pdf << CombinePDF.load("file1.pdf")
pdf << CombinePDF.load("file2.pdf")
pdf.save "combined.pdf"

(CombinePDF.load("file1.pdf") << CombinePDF.load("file2.pdf") << CombinePDF.load("file3.pdf")).save("combined.pdf")

pdf = CombinePDF.new
i = 0
CombinePDF.load("file.pdf").pages.each do |page|
i += 1
pdf << page if i.even?
end
pdf.save "even_pages.pdf"

company_logo = CombinePDF.load("company_logo.pdf").pages[0]
pdf = CombinePDF.load "content_file.pdf"
pdf.pages.each {|page| page << company_logo}
pdf.save "content_with_logo.pdf"

pdf.pages(nil, false).each {|page| page << stamp_page}

pdf = CombinePDF.load "file_to_number.pdf"
pdf.number_pages
pdf.save "file_with_numbering.pdf"

pdf = CombinePDF.load("file.pdf")

pdf_data = prawn_pdf_document.render
pdf = CombinePDF.parse(pdf_data)

require 'combine_pdf'
require 'net/http'
url = "https://example.com/my.pdf"
pdf = CombinePDF.parse Net::HTTP.get_response(URI.parse(url)).body

send_data combined_file.to_pdf, filename: "combined.pdf", type: "application/pdf"

status 200
body combined_file.to_pdf
headers 'content-type' => "application/pdf"

new_pdf = CombinePDF.new
new_pdf << CombinePDF.load(pdf_file, allow_optional_content: true)
attachments.each { |att| new_pdf << CombinePDF.load(att, allow_optional_content: true) }

```




