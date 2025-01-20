# abc


-- Table: public.cm_customer_request

-- DROP TABLE IF EXISTS public.cm_customer_request;

CREATE TABLE IF NOT EXISTS public.cm_customer_request
(
    id bigint NOT NULL GENERATED ALWAYS AS IDENTITY ( INCREMENT 1 START 1 MINVALUE 1 MAXVALUE 9223372036854775807 CACHE 1 ),
    cm_customer_code character varying(255) COLLATE pg_catalog."default" NOT NULL,
    lading_code character varying(50) COLLATE pg_catalog."default" NOT NULL,
    contact_phone character varying(20) COLLATE pg_catalog."default" NOT NULL,
    request_content text COLLATE pg_catalog."default",
    note text COLLATE pg_catalog."default",
    created timestamp without time zone,
    createdby bigint,
    updated timestamp without time zone,
    updatedby bigint,
    isactive boolean DEFAULT true,
    isdeleted boolean DEFAULT false,
    request_type character varying(50) COLLATE pg_catalog."default" NOT NULL DEFAULT 'Unknown'::character varying,
    reception_channel character varying(50) COLLATE pg_catalog."default" NOT NULL DEFAULT 'Unknown'::character varying,
    CONSTRAINT cm_customer_request_pk PRIMARY KEY (id)
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.cm_customer_request
    OWNER to postgres;
